# WLC configuration
1.1. For THE vmware this is the operating system:

<img width="451" height="443" alt="image" src="https://github.com/user-attachments/assets/2368e2ff-497a-44b2-a5f7-c63ec3086e3e" />

1.2. MAKE SURE YOU VM SETTINGS IS LIKE THIS:

<img width="758" height="728" alt="image" src="https://github.com/user-attachments/assets/979d8fb8-a110-4f74-bd86-804b22659a9e" />

1.3. to make it quiet

```bash
enable
config t
no logging console
exit
```

1.4. After booting up paste this in the wlc:

```bash
config t
username admin privilege 15 secret C1sc0123
line vty 0 48
login local
exec-timeout 0 0
int vlan1 
no shut
ip address dhcp
do sh ip int bri
```

1.5. Make sure you have this ip and still NAT on the network adapter:

<img width="688" height="80" alt="image" src="https://github.com/user-attachments/assets/d0ff632a-f1ca-4674-93b8-25a1998753b7" />

1.6. now you will access the ip 208.8.8.148 or any given ip in VLAN 1

1.7. CREdentials
 User:     admin
 Password: C1sc0123
 
<img width="1447" height="781" alt="image" src="https://github.com/user-attachments/assets/0a1c794b-b50a-4cef-ad5e-c2b6a5ddba98" />

1.8. after you login type all this in the blank space

<img width="1152" height="777" alt="image" src="https://github.com/user-attachments/assets/77b05d94-91ba-4fbf-89cc-b7fbcff88521" />


1.9. click add

<img width="1490" height="796" alt="image" src="https://github.com/user-attachments/assets/3a8a6436-d3e7-46b9-b61d-10c08f3fb061" />

1.10. after adding, put your network name and a pre shared password.

<img width="811" height="425" alt="image" src="https://github.com/user-attachments/assets/8c717030-ab33-4a58-899c-41eeeebf1394" />

1.11 click Next

<img width="1523" height="403" alt="image" src="https://github.com/user-attachments/assets/ce7aafd2-5c2d-4606-b128-c387fbba69f4" />

1.12. change rsa size to 2048 and add password.

<img width="1500" height="849" alt="image" src="https://github.com/user-attachments/assets/b0c66718-9f8b-4074-a38e-16d2f9bff1c6" />

1.13. this will be the summary, if you are oaky with it, click finish.

<img width="1485" height="858" alt="image" src="https://github.com/user-attachments/assets/698f5bc4-bd5d-4749-9f01-83d782272cd6" />

1.14. after clicking finish it will get stuck and now go back to the vmware network adapater ang change it to bridged and replicate.

<img width="768" height="733" alt="image" src="https://github.com/user-attachments/assets/71f5add3-31ed-42c3-a3de-19c67c77c314" />

1.15. after changing type this command and wait to show the 10.12.1.7

```bash
sh ip int bri
```

<img width="686" height="112" alt="image" src="https://github.com/user-attachments/assets/ea566569-f4bb-4e4d-9ee7-3b9bd2d20c73" />

1.16. access now the 10.12.1.7 in edge browser

CREDENTIALS:
username: admuin
password: C1sc0123

1.17. after getting to the UI of the 10.12.1.7 the cisco website, paste this command in the wlc. This command helps the ap to connect to the trsutpoint in the WLC

```bash
enable
configure terminal
wireless management interface vlan 1       
end

wireless config vwlc-ssc key-size 2048 signature-algo sha256 password 0 C1sc0123


show wireless management trustpoint


enable
configure terminal
wireless management interface vlan 1
end

wireless config vwlc-ssc key-size 2048 signature-algo sha256 password 0 justfornow

show wireless management trustpoint
```

<img width="717" height="877" alt="image" src="https://github.com/user-attachments/assets/88bbd927-d2be-454f-b5f4-b785ef8aec03" />

1.17. to check type: 
```bash
show wireless manaegemnt trustpoint
```

<img width="498" height="102" alt="image" src="https://github.com/user-attachments/assets/95305e12-17b6-47e0-9c2c-cf05471c3267" />

1.18. this will be the outcome, the 2 on the access point indicate that your AP is connected now.

<img width="1897" height="676" alt="image" src="https://github.com/user-attachments/assets/451bcd3d-05d3-4cf6-b9d7-54fa593c26dc" />

---

# CONNECTING TO THE WLAN MADE  

1.1. we will create a policy for real woprld experience. 

<img width="1508" height="878" alt="image" src="https://github.com/user-attachments/assets/c5110c29-9807-41c6-a5a8-4273bef10d57" />

1.2. CLICK ADD its in the upper left corner.

<img width="1884" height="872" alt="image" src="https://github.com/user-attachments/assets/d3ec4865-f1c0-40b5-8000-4bf91f5475ad" />

1.3. now add a name and click the status enabled

<img width="1839" height="890" alt="image" src="https://github.com/user-attachments/assets/380df721-e658-4acf-82e2-108fb814de05" />

1.4. the outcome should be like this:

<img width="1852" height="577" alt="image" src="https://github.com/user-attachments/assets/5873d006-1ea2-4aca-b6e9-64297f165131" />

1.5. after adding policy now we will go to the tags

<img width="1447" height="859" alt="image" src="https://github.com/user-attachments/assets/d61e5255-4ff8-4d1b-bca8-71bed9fb9bf0" />

1.6. click add again in the upper left corner

<img width="1902" height="782" alt="image" src="https://github.com/user-attachments/assets/a0cd9013-d372-4378-9bc6-d308cd7384f5" />

1.7. after click of the add button, put name you want and description and for the wlan policy you add the wifinate and the policy profile is the policy you made earlier 

<img width="1561" height="849" alt="image" src="https://github.com/user-attachments/assets/a45fe4cf-6862-44e5-b6e1-0275ecae4acd" />

1.8. now click the check button befopre apllying to device, this will be the outcome

<img width="1561" height="849" alt="image" src="https://github.com/user-attachments/assets/39dc4048-6b04-436f-82f3-e74201620b05" />

1.9. click apply to device

<img width="1904" height="860" alt="image" src="https://github.com/user-attachments/assets/c37bf346-e55c-4e97-a512-11bca2041b60" />

1.10. now go to the access points under wireless label

<img width="1912" height="895" alt="image" src="https://github.com/user-attachments/assets/edea070e-d9f7-44d0-9447-78547906c16d" />

1.11. make sure the one connected to your switch is seen in the GUI

<img width="1898" height="891" alt="image" src="https://github.com/user-attachments/assets/48962b21-12ef-47d0-bad2-f632e00ae712" />

1.12. now click any AP you have there or the 1st AP and this will be the outcome after you click it:

<img width="1901" height="928" alt="image" src="https://github.com/user-attachments/assets/8a4cf941-3a31-4a24-8220-62d3e71bc387" />


1.13. now we made the policy and the tags, in that circled area you should see the tags you made.

<img width="1901" height="928" alt="image" src="https://github.com/user-attachments/assets/5c3cc864-1f15-4f15-a0a9-993682b6403b" />

<img width="1899" height="889" alt="image" src="https://github.com/user-attachments/assets/d3e5bd52-40b2-4a66-ab9b-c60f6d067aad" />

1.14. after choosing the policy click "update & apply to device"

<img width="1907" height="881" alt="image" src="https://github.com/user-attachments/assets/624b80c5-2d88-489e-a178-444ee85b0cf2" />

1.15. take ntoe the AP WILL BE GONE BECAUSE IT WILL REFRESH AND IT WILL BOOTUP AGAIN just refresh the browser and make sure the ap is now UP again

<img width="1886" height="951" alt="image" src="https://github.com/user-attachments/assets/7c4148e4-3191-4d59-93d7-a0bed546368e" />

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


# IF THE DHCP IS NOT CONNECTING THIS IS THE FIX PROBLEM
1.1 if ever you already created all of it but still buffering to get connected to the wifi you made do this.

1.2. paste this command in the WLC: On WLC, correct helper to point to switch:

```bash
conf t
interface vlan 1
 ip helper-address 10.12.1.4
end
write mem

```

1.3. now next for the switch: On switch, confirm your pool matches:

```bash
ip dhcp pool VLAN1-POOL
 network 10.12.1.0 255.255.255.0
 default-router 10.12.1.7
 dns-server 8.8.8.8
```

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# NOW ADDING SOME WLAN MORE

1.1. go to the hambuger style again in the left side and under tags and progiles click wlan

<img width="1874" height="941" alt="image" src="https://github.com/user-attachments/assets/e79d6b31-858c-4214-9bcf-d27b8cbb2b7c" />

1.2. click add

<img width="1861" height="936" alt="image" src="https://github.com/user-attachments/assets/447c44f2-c10e-4a98-a98f-42d156437b47" />


1.3. put profile name and SSID and make the status enabled


<img width="1879" height="910" alt="image" src="https://github.com/user-attachments/assets/0d149bdb-f140-4a33-b63b-e3f449f8e889" />

1.3.1. make sure the security layer 2 is check PSK like this:

<img width="1909" height="942" alt="image" src="https://github.com/user-attachments/assets/72cb1d56-83c5-4b71-a05a-f25fc5379c6f" />


1.4. apply to device.

1.5. now go back to the hamburger style, and lcick tag because we will add the wifirian to the tags so it can be scanned also. 

<img width="1817" height="936" alt="image" src="https://github.com/user-attachments/assets/f6f00221-0ced-4936-bd26-6f48544f58a7" />

1.6. now click rivan tag

<img width="1897" height="943" alt="image" src="https://github.com/user-attachments/assets/162b63d4-2bda-487b-96e2-36557ed3b286" />

1.7. click add

<img width="1902" height="932" alt="image" src="https://github.com/user-attachments/assets/00df7c04-d5e4-4ef3-bacf-2c95e53c972c" />

1.8. now we will add the profile and the policy profile also this should be the outcome:

<img width="797" height="878" alt="image" src="https://github.com/user-attachments/assets/d378cd67-a17f-4460-91a9-4a2d8ec21c58" />

1.9. click the check button before doing update & apply to device

<img width="1897" height="935" alt="image" src="https://github.com/user-attachments/assets/828e8160-7488-4ac3-854b-a671d3a6fd33" />


# YOU CAN NOW CONNECT THE TO THE WIFI THAT YOU MADE!! CONGRATULATIONS!!


# THE END








































