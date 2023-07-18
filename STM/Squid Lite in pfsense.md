![pfSense home arpa - System_ Package Manager_ Available Packages - Google Chrome 28-06-2023 18_40_41](https://github.com/shubnimkar/Alpha-one/assets/46809421/cca1f1ba-10b0-460c-bbb3-cb0f748dee44)

![pfSense home arpa - System_ Package Manager_ Package Installer - Google Chrome 28-06-2023 18_41_46](https://github.com/shubnimkar/Alpha-one/assets/46809421/ea9a33c5-460d-4e60-9e23-9001db612c8b)

![pfSense home arpa - System_ Package Manager_ Package Installer - Google Chrome 28-06-2023 18_49_11](https://github.com/shubnimkar/Alpha-one/assets/46809421/ffeb0bdf-342a-491d-81f8-c75bb70287ac)

status > squid proxy> reports
Username used to access lighttpd. (Default: admin)
Password used to access lighttpd. (Default: pfsense)

![sq](https://github.com/shubnimkar/Alpha-one/assets/46809421/0f9265f7-a228-4ca8-80be-41dc7aa81614)
save > refreshfull

![1](https://github.com/shubnimkar/Alpha-one/assets/46809421/0a4cec12-3eb4-40f4-9718-f4459890f4e5)

open lightsquid
![LightSquid __ Index - Google Chrome 28-06-2023 18_59_35](https://github.com/shubnimkar/Alpha-one/assets/46809421/ebdfbf78-6bc0-47f5-a4dd-aee48cd82aa5)

![LightSquid __ User Detail - Google Chrome 28-06-2023 19_06_14](https://github.com/shubnimkar/Alpha-one/assets/46809421/9988f90a-e3a1-41ab-bd40-ddf472e9c9a8)

AIM : bahar se cleint machine pe bana page access karna managta hai

take centos client

ab yaha pe pfsense ka nat ip dena padgea dns me warna nahi chalega ya phr har bar reslov.conf me edit krna padega , so sidha add kr do nmtui me 

![ping](https://github.com/shubnimkar/Alpha-one/assets/46809421/5d729b5e-c3a4-4dd2-903e-3c82a2bc871c)

install apache yum install httpd /apache2 (ubuntu)

cd /var/www/html
vim index.html
go to machine ip host-only nd you will see the page

bahar access nahi hoga to selinux 0 krna padega

Firewall>NATPort >Forward> add >Edit
![pfSense home arpa - Firewall_ NAT_ Port Forward_ Edit - Google Chrome 28-06-2023 20_17_19](https://github.com/shubnimkar/Alpha-one/assets/46809421/ce072d2b-e1d0-4ffd-86f8-61524cd85f21)
save
 apply
 
![pfSense home arpa - Firewall_ NAT_ Port Forward - Google Chrome 28-06-2023 20_14_43](https://github.com/shubnimkar/Alpha-one/assets/46809421/dc43ceac-c283-413c-81fc-15d94e5b4a39)


firewall > rules 
![pfSense home arpa - Firewall_ Rules_ WAN - Google Chrome 28-06-2023 20_19_51](https://github.com/shubnimkar/Alpha-one/assets/46809421/68150510-fae8-43d7-b64b-20c29803fd12)
![pfSense home arpa - Firewall_ Rules_ WAN - Google Chrome 28-06-2023 19_51_40](https://github.com/shubnimkar/Alpha-one/assets/46809421/58c76a94-5e6b-42b4-8fe8-ac3c3e6fa89b)
![pfSense home arpa - Firewall_ Rules_ WAN - Google Chrome 28-06-2023 19_51_52](https://github.com/shubnimkar/Alpha-one/assets/46809421/dc3f3344-65cc-46df-9abb-8f907b24d343)
![pfSense home arpa - Firewall_ Rules_ WAN - Google Chrome 28-06-2023 20_12_42](https://github.com/shubnimkar/Alpha-one/assets/46809421/a1867ccd-e7af-442a-bc20-1657843441de)

goto edit on RFC 1918 networks	

save
 apply

go on pfsense nat address 
