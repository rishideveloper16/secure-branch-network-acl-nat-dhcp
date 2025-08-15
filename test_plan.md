# Test Plan
1) PCs in VLAN10 & VLAN20 obtain DHCP IPs.
2) Ping between VLANs (10 ↔ 20) = should work.
3) From VLAN10, try `telnet 192.168.10.1` = should be BLOCKED by ACL.
4) From any VLAN, ping 8.8.8.8 = should work (NAT).
5) `show ip nat translations` shows PAT entries.
6) `show access-lists 100` shows hit counts increasing.
