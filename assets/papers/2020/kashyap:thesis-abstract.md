Over the past decade, multicore machines have become the norm.
A single machine is capable of having thousands of hardware threads
or cores. Even cloud providers offer such large multicore machines for
data processing engines and databases. Thus, a fundamental question
arises is how efficient are existing synchronization primitives
---timestamping and locking---that developers use for designing
concurrent, scalable, and performant applications. This dissertation
focuses on understanding the scalability aspect of these primitives,
and presents new algorithms and approaches, that either leverage the
hardware or the application domain knowledge, to scale up to hundreds
of cores.

First, the thesis presents Ordo, a scalable ordering or timestamping
primitive, that forms the basis of designing scalable timestamp-based
concurrency control mechanisms. Ordo relies on invariant hardware
clocks and provides a notion of a globally synchronized clock within
a machine. We use the Ordo primitive to redesign a synchronization
mechanism and concurrency control mechanisms in databases and software
transactional memory.

Later, this thesis focuses on the scalability aspect of locks in
both virtualized and non-virtualized scenarios. In a virtualized
environment, we identify that these locks suffer from various
preemption issues due to a semantic gap between the hypervisor
scheduler and a virtual machine scheduler---the double scheduling
problem. We address this problem by bridging this gap, in which
both the hypervisor and virtual machines share minimal scheduling
information to avoid the preemption problems.


Finally, we focus on the design of lock algorithms in general. We find
that locks in practice have discrepancies from locks in design.
For example, popular spinlocks suffer from excessive cache-line
bouncing in multicore (NUMA) systems, while state-of-the-art locks
exhibit sub-par single-thread performance.  We classify several
dominating factors that impact the performance of lock algorithms.
We then propose a new technique, shuffling, that can dynamically
accommodate all these factors, without slowing down the critical path
of the lock.  The key idea of shuffling is to re-order the queue of
threads waiting to acquire the lock with some pre-established policy.
Using shuffling, we propose a family of locking algorithms, called
SHFLLOCKS that respect all factors, efficiently utilize waiters,
and achieve the best performance.
