# Secure Branch Network – ACL, NAT & DHCP (Cisco IOS)

Small branch office topology with:
- Two VLANs: Users (VLAN 10) & Admin (VLAN 20)
- Router-on-a-stick for inter-VLAN routing
- **ACL** to restrict Users from reaching router management but allow internet
- **NAT Overload (PAT)** for internet access
- **DHCP** pools per VLAN

## Topology
Switch (VLAN10, VLAN20) ↔ Router (G0/0.10, G0/0.20) ↔ ISP/Internet

## IP Plan
- VLAN10 Users: 192.168.10.0/24, GW 192.168.10.1
- VLAN20 Admin: 192.168.20.0/24, GW 192.168.20.1
- WAN/Outside: 203.0.113.2/30 (router), 203.0.113.1/30 (ISP)

## Files
- `router_config.txt` – full router commands
- `switch_config.txt` – VLAN + trunks + access ports
- `test_plan.md` – pings & verification steps
- `topology.png` – (screenshot from Packet Tracer / diagram)

## How to run (Packet Tracer)
1. Create VLAN 10 & 20 on switch, set trunk to router, access ports to PCs.
2. On router, create sub-interfaces, apply `router_config.txt`.
3. Verify DHCP leases on PCs, test inter-VLAN & internet via NAT.
4. Check ACL blocks where expected (e.g., Users → router vty).

## Deliverables
- `SecureBranch.pkt` (Packet Tracer file)
- Screenshots of: DHCP leases, NAT translations, ACL hit counters
