    Distributed file systems (DFSes) are prone to bugs.
    Although numerous bug-finding techniques have been applied to DFSes,
    static analysis does not scale well with the sheer complexity of DFS codebases
    while dynamic methods (e.g., regression testing) are limited by the quality of test cases.
    Although both can be improved by pouring in manual effort,
    they are less practical when facing a diverse set of real-world DFSes.
    Fuzzing, on the other hand, has shown great success in local systems.
    However, several problems exist if we apply existing fuzzers
    to DFSes as they
    1) cannot test multiple components of DFSes holistically;
    2) miss the critical testing aspects of DFSes (e.g., distributed faults);
    3) have not yet explored the practical state representations as fuzzing feedback; and
    4) lack checkers for asserting semantic bugs unique to DFSes.

    In this paper,
    we introduce Monarch,
    a multi-node fuzzing framework
    to test all POSIX-compliant DFSes under one umbrella.
    Monarch pioneers push-button fuzzing for DFSes
    with a new set of building blocks to the fuzzing toolbox:
    1) A multi-node fuzzing architecture for testing diverse DFSes from a holistic perspective;
    2) A two-step mutator for testing DFSes with syscalls and faults;
    3) Practical execution state representations with a unified coverage collection scheme across execution contexts;
    4) A new DFSes semantic checker SYMSC.
    We applied Monarch to six DFSes and uncovered a total of 48 bugs,
    including a bug whose existence can be traced back to the initial release of the DFSes.