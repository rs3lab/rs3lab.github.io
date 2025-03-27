With the "non-hierarchical" trend in emerging storage media, 
the philosophy of hierarchy inevitably falls short in fully 
leveraging the combined bandwidth of multiple devices. 
In this paper, we propose a horizontally structured storage 
architecture that leverages the combined capabilities of 
heterogeneous devices. 
We introduce PolyStore, a meta layer atop storage medium-optimized 
file systems that spans userspace and the OS, allowing applications 
to access multiple storage devices concurrently with transparent, 
fine-grained data placement. 
PolyStore maximizes cumulative storage bandwidth and reduces 
hardware and software bottlenecks without compromising important 
properties such as sharing and security. 
Our evaluations show that PolyStore achieves 1.11X- 9.38X performance 
gains for micro-benchmarks and 1.52X- 2.02X for real-world 
applications across various device configurations.
