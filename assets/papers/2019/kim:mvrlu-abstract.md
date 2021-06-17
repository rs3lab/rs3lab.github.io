This paper presents multi-version read-log-update (MVRLU), an extension
of the read-log-update (RLU) synchronization mechanism. While
RLU has many merits including an intuitive programming model and
excellent performance for read-mostly workloads, we observed that the
performance of RLU significantly drops in workloads with more write
operations. The core problem is that RLU manages only two versions. %
and its log reclamation is synchronous.  To overcome such limitation,
we extend RLU to support multi-versioning and propose new techniques
to make multi-versioning efficient. At the core of MVRLU design is
concurrent autonomous garbage collection, which prevents reclaiming
invisible versions being a bottleneck, and reduces the version
traversal overhead - the main overhead of multi-version design.
We extensively evaluate MVRLU with the state-of-the-art synchronization
mechanisms, including RCU, RLU, software transactional memory (STM),
and lock-free approaches, on concurrent data structures and real-world
applications (database concurrency control and in-memory key-value
store). Our evaluation shows that MVRLU significantly outperforms
other techniques for a wide range of workloads with varying contention
levels and data-set size.
