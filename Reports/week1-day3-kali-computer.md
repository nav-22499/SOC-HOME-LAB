
### Windows Firewall ICMP Troubleshooting

Issue:
Kali Linux could not successfully ping the Windows endpoint.

Investigation:
Traffic was being blocked by Windows Defender Firewall ICMP rules.

Resolution:
Enabled:
File and Printer Sharing (Echo Request - ICMPv4-In)

Result:
Successful connectivity established between Kali and Windows systems.
