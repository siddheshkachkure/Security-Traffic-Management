Services > Snort > Interfaces
![pfSense home arpa - Services_ Snort_ Interface Settings_ WAN - Rules - Google Chrome 30-06-2023 10_14_50](https://github.com/shubnimkar/Alpha-one/assets/46809421/49e0812a-58de-48d3-adf5-97c772f2b2c3)

Services > Snort > WAN - Interface Settings
![pfSense home arpa - Services_ Snort_ Alerts - Google Chrome 30-06-2023 10_18_17](https://github.com/shubnimkar/Alpha-one/assets/46809421/29c76bfb-7f98-4f01-bafa-2c01e4833285)
![pfSense home arpa - Services_ Snort_ Alerts - Google Chrome 30-06-2023 10_18_23](https://github.com/shubnimkar/Alpha-one/assets/46809421/6c4b88e3-bb74-4874-b317-16d33083532a)

Services > Snort > Interface Settings > WAN - Categories
![pfSense home arpa - Services_ Snort_ Interface Settings_ WAN - Categories - Google Chrome 30-06-2023 10_19_42](https://github.com/shubnimkar/Alpha-one/assets/46809421/c3068440-f8ca-4bef-91d1-278710d3eaa1)
![pfSense home arpa - Services_ Snort_ Interface Settings_ WAN - Categories - Google Chrome 30-06-2023 10_19_51](https://github.com/shubnimkar/Alpha-one/assets/46809421/eec11bd4-c37d-4e41-810b-f88c1c062ff5)

ServicesSnortInterface SettingsWAN - Rules
![pfSense home arpa - Services_ Snort_ Interface Settings_ WAN - Rules - Google Chrome 30-06-2023 10_20_29](https://github.com/shubnimkar/Alpha-one/assets/46809421/848b26e0-cb02-4c3b-a575-6e0e7a1cc6a9)

ServicesSnortGlobal Settings
![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 30-06-2023 10_15_58](https://github.com/shubnimkar/Alpha-one/assets/46809421/3765536c-7301-483f-8cff-5780b8deeaf9)
![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 30-06-2023 10_16_03](https://github.com/shubnimkar/Alpha-one/assets/46809421/5575c8c0-4da0-4dee-99a1-25b59a30b610)

Interface Settings Overview
![pfSense home arpa - Services_ Snort_ Interfaces - Google Chrome 30-06-2023 10_20_54](https://github.com/shubnimkar/Alpha-one/assets/46809421/786d7274-20c5-4851-a4e1-2f25d68d5edf)

Alerts
![pfSense home arpa - Services_ Snort_ Alerts - Google Chrome 30-06-2023 10_16_50](https://github.com/shubnimkar/Alpha-one/assets/46809421/b4983588-09d6-4300-a7c3-3e3876f5610a)


# for packet of more size here >256
![pfSense home arpa - Services_ Snort_ Interfaces - Google Chrome 30-06-2023 11_07_50](https://github.com/shubnimkar/Alpha-one/assets/46809421/9efdc739-b001-49a0-86b5-a0736b757d7e)
![pfSense home arpa - Services_ Snort_ Interfaces - Google Chrome 30-06-2023 11_08_50](https://github.com/shubnimkar/Alpha-one/assets/46809421/2e9c284e-9e9d-4f71-97a0-56191d5b9f24)

# for ttl < 3 (traceroute)
![pfSense home arpa - Services_ Snort_ Interfaces - Google Chrome 30-06-2023 11_20_52](https://github.com/shubnimkar/Alpha-one/assets/46809421/f18d427f-218a-4339-b9dd-98952f8eb66f)

goto client machine and ping kali ip with command 
ping -t 2 192.168.100.155 (KALI IP)
![ping](https://github.com/shubnimkar/Alpha-one/assets/46809421/cc0222df-2c0b-450f-8162-66798ae19987)
![pfSense home arpa - Services_ Snort_ Interfaces - Google Chrome 30-06-2023 11_23_25](https://github.com/shubnimkar/Alpha-one/assets/46809421/f122998a-e406-4261-81b0-795e50c26e0f)


# NMAP
goto kali 

wireshark start

nmap -sS 192.168.100.155(pfsense nat)
![ka](https://github.com/shubnimkar/Alpha-one/assets/46809421/91ecf4bd-86f1-4fa2-88ac-f6b0c3bc6666)

once command is over then stop wireshark
![Kali - VMware Workstation 30-06-2023 11_30_12](https://github.com/shubnimkar/Alpha-one/assets/46809421/c9a9020d-83bc-45d8-9cf7-a0d2d3f96358)


then rule for this 
![pfSense home arpa - Services_ Snort_ Alerts - Google Chrome 30-06-2023 11_52_36](https://github.com/shubnimkar/Alpha-one/assets/46809421/2110f56b-dd21-48fa-a884-aadf7da1e166)

alerts
![pfSense home arpa - Services_ Snort_ Alerts - Google Chrome 30-06-2023 11_52_26](https://github.com/shubnimkar/Alpha-one/assets/46809421/c40a733f-bc5e-4156-b52d-5b2f46dd4888)

# ALLOWING SSH FROM NETWORK TO CLIENT
FirewallNATPort Forward
![pfSense home arpa - Firewall_ NAT_ Port Forward - Google Chrome 30-06-2023 11_53_19](https://github.com/shubnimkar/Alpha-one/assets/46809421/95148219-8b44-4850-baa2-b95e85561024)

FirewallNATPort ForwardEdit
![pfSense home arpa - Firewall_ NAT_ Port Forward - Google Chrome 30-06-2023 11_53_19](https://github.com/shubnimkar/Alpha-one/assets/46809421/fd0dc948-54cf-4083-8835-1f84fd3461e3)

![pfSense home arpa - Firewall_ NAT_ Port Forward - Google Chrome 30-06-2023 11_57_03](https://github.com/shubnimkar/Alpha-one/assets/46809421/2c0b5eaf-0839-4dd6-9670-e8902bec9e31)

![pfSense home arpa - Firewall_ NAT_ Port Forward - Google Chrome 30-06-2023 11_57_10](https://github.com/shubnimkar/Alpha-one/assets/46809421/5f6e029f-3832-4dc1-8bd4-4564ef5889b6)

![pfSense home arpa - Firewall_ NAT_ Port Forward - Google Chrome 30-06-2023 11_57_16](https://github.com/shubnimkar/Alpha-one/assets/46809421/5e7f42d6-08cf-4a99-9e28-49cea6adc011)

check for firewalld should be inactive
![fr](https://github.com/shubnimkar/Alpha-one/assets/46809421/d8025a4f-6ab8-474f-82c0-493ed53c12e1)


then goto kali SSH to client 

ssh root@192.168.100.155

![Capture](https://github.com/shubnimkar/Alpha-one/assets/46809421/dbab96cd-4b70-4801-ad42-0c470ea547f4)

if i want to get alert is ssh happened

then rule and go to kali n ssh client

![pfSense home arpa - Firewall_ NAT_ Port Forward - Google Chrome 30-06-2023 12_38_20](https://github.com/shubnimkar/Alpha-one/assets/46809421/695c71d2-f2f3-4125-a814-8a9238f3990b)

alert
![pfSense home arpa - Firewall_ NAT_ Port Forward - Google Chrome 30-06-2023 12_38_04](https://github.com/shubnimkar/Alpha-one/assets/46809421/77279bd9-a7af-4045-8c29-376ea98129f9)


NMAP NHI ANA CHAHIYE 
RuLE:

alert tcp any any -> 192.168.100.155 any (msg:"Possible NMAP Scan";flow:stateless;flags:S;detection_filter:track by_src, count 10,seconds 1;sid:1000005;)

![pfSense home arpa - Firewall_ NAT_ Port Forward - Google Chrome 30-06-2023 12_47_54](https://github.com/shubnimkar/Alpha-one/assets/46809421/881ff2a6-bec5-437a-8b93-1170303be8ab)
![pfSense home arpa - Firewall_ NAT_ Port Forward - Google Chrome 30-06-2023 12_48_00](https://github.com/shubnimkar/Alpha-one/assets/46809421/d077d49b-fa51-4a27-8ab8-11ed0ed6dbf8)



alert (abhi NMAP NHI AYEGA)
![pfSense home arpa - Firewall_ NAT_ Port Forward - Google Chrome 30-06-2023 12_49_43](https://github.com/shubnimkar/Alpha-one/assets/46809421/77c0ba47-5d16-4de8-98ed-077a9d303410)


# IPS

![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 30-06-2023 15_41_12](https://github.com/shubnimkar/Alpha-one/assets/46809421/9ac658c9-2d5f-4eb4-819f-f46d95c243a5)
![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 30-06-2023 15_41_02](https://github.com/shubnimkar/Alpha-one/assets/46809421/2c10d802-960b-4237-a292-0ef9430c6c22)

![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 30-06-2023 15_41_25](https://github.com/shubnimkar/Alpha-one/assets/46809421/eb1bced0-bf20-42c3-9e16-c2f5a1bbc54a)

![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 30-06-2023 15_42_16](https://github.com/shubnimkar/Alpha-one/assets/46809421/adc72cab-aaad-4d7f-9b36-06a43f716d9b)
![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 30-06-2023 15_42_22](https://github.com/shubnimkar/Alpha-one/assets/46809421/e5faf982-2576-4c18-833c-4a3a8f14d981)

![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 30-06-2023 15_43_59](https://github.com/shubnimkar/Alpha-one/assets/46809421/bcc9e6cf-72ee-4fe1-a785-f61d2547f48c)
