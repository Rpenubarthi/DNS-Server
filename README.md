### High-Level Approach 
1. Followed each step of the implementation strategy to pass tests incrementally.  
3. Handled iterative resolution, referral sequencing, and bailiwick checks.  
4. Monitored DNS flags and error codes (e.g., AA, RD, RA, NXDOMAIN, SERVFAIL) for correctness.  
5. Managed UDP socket communication between client and upstream servers to ensure reliable query handling.


### Challenges
Implementing the server required constant reiteration and fixing errors/bugs in the code. It required referral sequencing and bailiwick checks, as well as accurate handling of DNS flags and error codes (e.g., AA, RD, RA, NXDOMAIN, SERVFAIL). Ensuring reliable UDP socket handling—separating client and upstream traffic—while launching the script correctly in a Unix environment added additional complexity. The most challenging part was completing bullet 5 of the implementation strategy, which required handling concurrent queries while other queries were still being processed.

### Key Features
- Zone-file automation: Used RR.fromZone and DNSLabel to automatically extract origins and resource records from zone files.  
- Dual-socket architecture: Maintained separate UDP sockets for client and upstream traffic to ensure reliable and orderly packet handling.  
- Caching and TTL management: Stored upstream responses in self.dns_cache with timestamp checks to reduce repeated queries to the root server.


### Testing
Testing mostly relied on system logs between the client and upstream servers to verify the proper peer connections and paths were taking place. These logs also helped with debugging buggy implementations.
