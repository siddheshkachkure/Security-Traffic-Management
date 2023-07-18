NIDS : NETWORK BASED INTRUSION DETECTION SYSTEM
HIDS : HOST BASED INTRUSION DETECTION SYSTEM

pele pfsense aur webserver shuru kar dena

kali :

wireshark jana hai ens0 phr start karna
phr apna pfsnse wala nat ip dena browser pe aur apna site open hona chahiye
uske bad kuch time me stop krna and file me jake save kro documents> incident> tcpdump.pcap
https://www.malware-traffic-analysis.net/
then
https://www.malware-traffic-analysis.net/training-exercises.html
then
![Kali - VMware Workstation 29-06-2023 14_32_24](https://github.com/shubnimkar/Alpha-one/assets/46809421/4ab44476-c5ca-4cd3-a645-fd28b681e4ff)
![Kali - VMware Workstation 29-06-2023 14_32_49](https://github.com/shubnimkar/Alpha-one/assets/46809421/908111a1-9b23-41bc-ab60-f6bcd2e5cffe)

password: infected

then wireshark me kholo

nbns protocol hoga to ip windows machine ka to phr apan dekh sakte machine k naam
![Kali - VMware Workstation 29-06-2023 14_39_06](https://github.com/shubnimkar/Alpha-one/assets/46809421/10a7f0db-494b-4656-b062-5752eea6c748)

yaha machine ka naam dekho
![Kali - VMware Workstation 29-06-2023 14_43_21](https://github.com/shubnimkar/Alpha-one/assets/46809421/17d21756-6bbe-4c0c-9b1c-5e92b6bb36e1)


kerberos dala aur dekha sidha naam mila mnachine ka
![Kali - VMware Workstation 29-06-2023 14_53_11](https://github.com/shubnimkar/Alpha-one/assets/46809421/22128b09-cd0d-4fe1-8f18-36cb76e1f62d)

username
![Kali - VMware Workstation 29-06-2023 14_55_20](https://github.com/shubnimkar/Alpha-one/assets/46809421/1de3089c-6787-4e4d-97c1-fd654742e3b7) 10.0.0.149
![Kali - VMware Workstation 29-06-2023 14_56_22](https://github.com/shubnimkar/Alpha-one/assets/46809421/0cf2c4df-9f3a-4eec-86dc-88100a1838a6) 10.0.0.169


cnamestring pe rightclick > apply as column to find all users in system
![Kali - VMware Workstation 29-06-2023 14_58_37](https://github.com/shubnimkar/Alpha-one/assets/46809421/cfb9e279-1d31-499a-9a54-bb12086e0b3e)

virustotal.com
#########################################################################
touch file1
    9  Im using kali linux > file1
   10  echo Im using kali linux > file1
   11  cat file1
   12  md5sum file1
   13  echo Im hashing > file1
   14  md5sum file1
   15  mv file1 test1
   16  md5sum test1
┌──(drax㉿kali)-[~]
└─$ touch file1      
                                                                             
┌──(drax㉿kali)-[~]
└─$ Im using kali linux > file1 
Im: command not found
                                                                             
┌──(drax㉿kali)-[~]
└─$ echo Im using kali linux > file1
                                                                             
┌──(drax㉿kali)-[~]
└─$ cat file1
Im using kali linux
                                                                             
┌──(drax㉿kali)-[~]
└─$ md5sum file1 
571098bade9b4a86b48444c87e4fed42  file1
                                                                             
┌──(drax㉿kali)-[~]
└─$ echo Im hashing > file1         
                                                                             
┌──(drax㉿kali)-[~]
└─$ md5sum file1           
1a90b066fb667a511eabe97c7fafa2e3  file1
                                                                             
┌──(drax㉿kali)-[~]
└─$ mv file1 test1
                                                                             
┌──(drax㉿kali)-[~]
└─$ md5sum test1
1a90b066fb667a511eabe97c7fafa2e3  test1

################33333######################################################################
snort install kar lopfsense dash board se

![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 29-06-2023 17_00_05](https://github.com/shubnimkar/Alpha-one/assets/46809421/a94a9732-e2ad-4441-ac3f-244f2dae8446)
![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 29-06-2023 17_00_10](https://github.com/shubnimkar/Alpha-one/assets/46809421/e79409a8-d352-449e-aecb-fbe963332ac3)
![pfSense home arpa - Services_ Snort_ Interfaces - Google Chrome 29-06-2023 16_59_01](https://github.com/shubnimkar/Alpha-one/assets/46809421/33baaaaf-33fd-4fe5-8f82-36951016a72a)

ServicesSnortGlobal >Settings
![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 29-06-2023 17_05_11](https://github.com/shubnimkar/Alpha-one/assets/46809421/a25754f7-9cff-4b4d-9baf-1fe5f0776f26)
![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 29-06-2023 17_05_25](https://github.com/shubnimkar/Alpha-one/assets/46809421/509dc085-ea2e-4d33-ac8e-f5ec5e5a6c72)

Services>snort>updates
![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 29-06-2023 17_06_07](https://github.com/shubnimkar/Alpha-one/assets/46809421/3b6727c9-fbc7-4694-bb23-ebf0f40a9e57)
![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 29-06-2023 17_06_19](https://github.com/shubnimkar/Alpha-one/assets/46809421/527df1a2-c862-453b-a28e-7ab206daff68)
![pfSense home arpa - Services_ Snort_ Updates - Google Chrome 29-06-2023 19_40_51](https://github.com/shubnimkar/Alpha-one/assets/46809421/37158b96-dd91-4685-84f6-1ad813a70e9b)

make windows machine

go to kali linux

sudo mkdir /hacking
cd hacking
vi index.html
This is the hackers website !!!!
vi virus.py
this is virus

ServicesSnortWAN - Interface Settings

![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 29-06-2023 17_35_25](https://github.com/shubnimkar/Alpha-one/assets/46809421/eb9ce837-4a80-474e-9bc0-65315cdd78ba)
![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 29-06-2023 17_35_35](https://github.com/shubnimkar/Alpha-one/assets/46809421/efd731b5-6e17-49f9-bf73-95e1aad3c2f8)


wan cat same me
![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 29-06-2023 17_39_16](https://github.com/shubnimkar/Alpha-one/assets/46809421/534b532a-2b40-449e-aa51-c7a69d414442)
![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 29-06-2023 17_39_30](https://github.com/shubnimkar/Alpha-one/assets/46809421/a47ed1fa-1f4d-4ed8-a506-c97473b34876)


ServicesSnortInterface SettingsWAN - Rules
![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 29-06-2023 17_41_17](https://github.com/shubnimkar/Alpha-one/assets/46809421/31a95dfd-7d21-463b-a7aa-29a601bf4f21)
enable all
apply
![pfSense home arpa - Services_ Snort_ Global Settings - Google Chrome 29-06-2023 17_41_28](https://github.com/shubnimkar/Alpha-one/assets/46809421/7997d4a8-bd66-4b9f-996a-fd222ac5bc59)
then we see this page

![Editing Alpha-one_INTRUSION DETECTION SYSTEM md at master · shubnimkar_Alpha-one · GitHub - Google Chrome 29-06-2023 17_55_07](https://github.com/shubnimkar/Alpha-one/assets/46809421/b0b562b9-23f1-4e39-815c-fe9572ff18f3)
start kar dena


![Alpha-one_INTRUSION DETECTION SYSTEM md at master · shubnimkar_Alpha-one - Google Chrome 29-06-2023 19_42_57](https://github.com/shubnimkar/Alpha-one/assets/46809421/42678a36-ce41-45b9-b93b-d932b6198c07)

then save karke wapis chalu karna hai service

go to client machine 
browser 192.168.100.155:8000 (kali ka ip with port jo set kia tha python server)
