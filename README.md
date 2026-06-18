# computer-in-network-but-ping-not-work

1. Check if ping is disabled by registry/group policy

Open CMD as Administrator:

netsh firewall show state

Then enable ICMP:

netsh advfirewall firewall add rule name="Allow Ping" protocol=icmpv4:8,any dir=in action=allow

Try ping again.

2. Check network discovery services

Press:

Win + R

Type:

services.msc

Make sure these are Running:

Function Discovery Provider Host
Function Discovery Resource Publication
SSDP Discovery
UPnP Device Host


4. Try name instead of IP
ping PC-NAME

Example:

ping OFFICE-PC
5. Check router isolation

Some routers have:

AP Isolation / Client Isolation

When enabled:

Internet works
File sharing may work in some cases
Ping fails

Disable it in router settings.
