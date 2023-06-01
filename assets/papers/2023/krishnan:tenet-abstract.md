Byte-addressable non-volatile memory (NVM) allows programs
to directly access storage using memory interface without
going through the expensive conventional storage stack.
However, direct access to NVM makes the NVM data vulnerable
to software bugs and hardware errors. This issue is critical
because, unlike DRAM, corrupted data can persist forever,
even after the system restart. Albeit the plethora of research on
NVM programs and systems, there is little focus on protecting
NVM data from software bugs and hardware errors.

In this paper, we propose TENET, a new NVM programming
framework, which guarantees memory safety and fault
tolerance to protect NVM data against software bugs and hardware
errors. TENET provides the popular persistent transactional
memory (PTM) programming model. TENET leverages
the concurrency guarantees (i.e., ACID properties) of PTM
to provide performant and cost-efficient memory safety and
fault tolerance. Our evaluations show that T ENET offers an
enhanced protection scope at a modest performance overhead
and storage cost as compared to other PTMs with partial or
no memory safety and fault tolerance support.
