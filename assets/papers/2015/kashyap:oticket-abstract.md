With increasing demand of big-data processing and faster in-memory
databases, cloud providers are gearing towards large virtualized
instances rather than horizontal scalability.

However, our experiments reveal that such instances in popular cloud
services (e.g., 32 vCPUs with 208 GB supported by Google Compute Engine)
do not achieve the desired scalability with increasing core count even
with a simple, embarrassingly parallel job (e.g., kernel compile). On a
serious note, the internal synchronization scheme (e.g., paravirtualized
ticket spinlock) of the virtualized instance on a machine with higher
core count (e.g., 80-core) dramatically degrades its overall performance.
Our finding is different from a previously well-known scalability problem
(lock contention problem), and occurs because of the sophisticated
optimization techniques implemented in the hypervisor, what we call --
sleepy spinlock anomaly. To solve this problem, we design and implement
oticket, a variant of paravirtualized ticket spinlock that effectively scales
the virtualized instances in both undersubscribed and oversubscribed environments.

