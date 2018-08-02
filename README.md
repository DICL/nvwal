# NVWAL
Emerging byte-addressable non-volatile memory is considered
an alternative storage device for database logs that
require persistency and high performance. In this work,
we develop NVWAL (NVRAM Write-Ahead Logging) for
SQLite. The proposed NVWAL is designed to exploit byteaddressable
NVRAM to maintain the write-ahead log and
to guarantee the failure atomicity and the durability of
a database transaction. The contribution of NVWAL consists
of three elements: (i) **byte-granularity differential logging
that effectively eliminates the excessive I/O overhead
of filesystem-based logging or journaling**, (ii) **transactionaware
lazy synchronization that reduces cache synchronization
overhead by two-thirds**, and (iii) **user-level heap management
of the NVRAM persistent WAL structure**, which
reduces the overhead of managing persistent objects.
We implemented NVWAL in SQLite and measured the
performance on a Nexus 5 smartphone and an NVRAM
emulation board - Tuna. Our performance study shows the
following: (i) the overhead of enforcing strict ordering of
NVRAM writes can be reduced via NVRAM-aware transaction
management. (ii) From the application performance
point of view, the overhead of guaranteeing failure atomicity
is negligible; the cache line flush overhead accounts for
only 0.8∼4.6% of transaction execution time. Therefore, application
performance is much less sensitive to the NVRAM
performance than we expected. Decreasing the NVRAM latency
by one-fifth (from 1942 nsec to 437 nsec), SQLite
achieves a mere 4% performance gain (from 2517 ins/sec
to 2621 ins/sec). (iii) Overall, when the write latency of
NVRAM is 2 usec, NVWAL increases SQLite performance
by at least 10x compared to that of WAL on flash memory
(from 541 ins/sec to 5812 ins/sec).

## Reference:
Wook-Hee Kim, Jinwoong Kim, Woongki Baek, Beomseok Nam and Youjip Won "NVWAL: Exploiting NVRAM in Write-Ahead-Logging", 21st International Conference on Architectural Support for Programming Languages and Operating Systems (ASPLOS '16), Atlanta, GA, Apr. 2016

http://dicl.skku.edu/publications/asplos16-nvwal.pdf

## Acknowledgement:

This research was supported by MKE/KEIT (No.10041608, Embedded System Software for New Memory based Smart Devices).
