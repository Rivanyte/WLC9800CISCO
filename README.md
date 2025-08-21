# WLC configuration
1.1. For THE vmware this is the operating system:
<img width="451" height="443" alt="image" src="https://github.com/user-attachments/assets/2368e2ff-497a-44b2-a5f7-c63ec3086e3e" />

1.2. MAKE SURE YOU VM SETTINGS IS LIKE THIS:
<img width="758" height="728" alt="image" src="https://github.com/user-attachments/assets/979d8fb8-a110-4f74-bd86-804b22659a9e" />

1.3. to make it quiet

'''bash
enable
config t
no logging console
'''

1.4. After booting up paste this in the wlc:

'''bash
config t
username admin privilege 15 secret C1sc0123
line vty 0 48
login local
exec-timeout 0 0
int vlan1 
no shut
ip address dhcp
do sh ip int bri
'''




