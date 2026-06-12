
Network Troubleshooting Lab (DHCP Fix)
Step 1: DHCP Failed

The PC could not get an IP address.

Step 2: Checked the problem

I ran ipconfig and saw:

IP = 169.254.x.x (bad IP)
No default gateway

This means DHCP is broken.

Step 3: Fixed DHCP on router

I fixed it using these commands:

enable
configure terminal
ip dhcp pool LAN_A
network 192.168.10.0 255.255.255.0
default-router 192.168.10.1
dns-server 8.8.8.8
end
Step 4: Tested fix

PC now gets a valid IP address.

Skills learned
DHCP troubleshooting
Router configuration
Using ipconfig
Fixing network problems
