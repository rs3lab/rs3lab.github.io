File systems are too large to be bug free. Although handwritten test suites
have been widely used to stress file systems, they can hardly keep up with the
rapid increase in file system size and complexity, leading to new bugs being
introduced. These bugs come in various flavors: buffer overflows to complicated
semantic bugs. Although bug-specific checkers exist, they generally lack a way
to explore file system states thoroughly. More importantly, no turnkey
solution exists that unifies the checking effort of various aspects of a file
system under one umbrella.

In this article, to highlight the potential of applying fuzzing to find any
type of file system bugs in a generic way, we propose Hydra, an extensible
fuzzing framework. Hydra provides building blocks for file system fuzzing,
including input mutators, feedback engines, test executors, and bug
post-processors. As a result, developers only need to focus on building the
core logic for finding bugs of their interests. We showcase the effectiveness
of Hydra with four checkers that hunt crash inconsistency, POSIX violations,
logic assertion failures, and memory errors. So far, Hydra has discovered 157
new bugs in Linux file systems, including three in verified file systems (FSCQ
and Yxv6).
