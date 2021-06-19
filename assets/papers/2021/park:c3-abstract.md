Kernel synchronization primitives are of paramount importance
to achieving good performance and scalability for applications.
However, they are usually invisible and out of the reach of application
developers.  Instead, kernel developers and synchronization experts
make all the decisions regarding kernel lock design.

In this paper, we propose _contextual concurrency control_ (C3),
a new paradigm that enables userspace applications to tune concurrency
control in the kernel.  C3 allows developers to change the behavior
and parameters of kernel locks, to switch between different lock
implementations and to dynamically profile one or multiple locks for
a specific scenario of interest.

To showcase this idea, we designed and implemented CONCORD, a framework
that allows a privileged userspace process to modify kernel locks on
the fly without re-compiling the existing code base.  We performed
a preliminary evaluation on two locks showing that CONCORD allows
userspace tuning of kernel locks without incurring significant
overhead.

