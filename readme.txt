The topology consist of a single Service Provide called ISP-1 (whose autonomous system number is 65510) providing L3 VPN service to two customers called CBT (65520) and ACME (AS 65515):
- Each PE is attached to each customer’s remote site, routing protocols used for peering is BGPv4 with Loopback 0 IP address used as Router-Id.
- The IGP protocol running inside ISP-1’s network is IS-IS (with process Id of 100), all NEs are configured as Level-2 only IS and networks are set to point-to-point circuits.
- MPLS is enabled on all P-routers and PEs internal interfaces, Loopback 0 IP address is used for LSR-Id, LDP is also enabled with default settings to build LSPs.
- MP-BGP peering is set up between PE-1 and PE-2 with address family VPNv4 to carry customer’s VPN IPv4 routes, each PE’s external interface are configured with a VPN Routing and Forwarding instance for each CE, name VPNAcme and VPNCbt respectively for ACME and CBT.
- Each CE is configured with Loopback 0 IP address as a hsot route (with /32 prefix), the objective is to achieve communication between CEs Loopbacks of a given customer.

Other features will be enabled on MPLS/IP domain: BFD to optimize IGP’s convergence process, MPLS-TE with RSVP-TE as control-plane protocol to set TE tunnels between NEs with explicit paths.
