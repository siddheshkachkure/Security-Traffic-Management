# Port forwarding using Pfsense firewall 

![LAB](https://github.com/shubnimkar/Alpha-one/assets/46809421/611fb99c-1d7d-4828-bd04-662c41616443)

# Problem statement : 
      We have to create two servers on two different machines (Windows and Linux),
      create a website page which we want to access from the outside network. 
      Now we want when we will put port :8000 then windows machine's website should be accessed,
      and when we put port :80 then linux website should be visible.

# Requirement :
              Virtual machines : 3
              Create:
                    one virtual machine having Pfsense 
                    one virtual machine having linux (I've installed centos 7.9)
                    one virtula machine having windows server (my version: 2016)
              
              And need snort installed in Pfsense


# Now machine set up:
## PFsense:

### Virtual Machine settings:

Network Adapters : NAT , HOST-ONLY

![ps](https://github.com/shubnimkar/Alpha-one/assets/46809421/236b7cf6-f79f-49fe-a9d1-483a4b928810)

#### Now configure pfsense  

                        Give IP and check if pfsense is getting both LAN & WAN IP addresses
                        Here I've given IP: 10.10.10.140 (FOR Pfsense LAN IP)

If you want know how to install and configure Pfsense click here [Pfsense installation & configuration](https://github.com/shubnimkar/Security-and-Traffic-Management/blob/master/PfSense.md)

### After configuration it'll look something like this :

![Pfsense new - VMware Workstation 30-06-2023 19_05_17](https://github.com/shubnimkar/Alpha-one/assets/46809421/82ef6084-b2c0-4d12-8abd-1dfb4031551c)


## Linux (Centos7)

Network Adapters : HOST-ONLY

#### Now configure IP for the same
      nmtui
      > manual IP
      > Set IP : 10.10.10.142 (In same network as pfsense LAN IP)
      > Gateway : 10.10.10.140 (IP of Pfsense)
      > DNS : 192.168.100.2 (WAN IP of Pfsense to access the internet)
                  

![STM2 - VMware Workstation 30-06-2023 19_12_31](https://github.com/shubnimkar/Alpha-one/assets/46809421/01e091b1-1ef9-40e8-b004-622c336d13f8)

#### Now check if you are getting same IP which you've given 

      ip a

![ip](https://github.com/shubnimkar/Alpha-one/assets/46809421/3caee3e8-355c-44b4-b792-5c568b7f6f03)

## Now Webserver installation and creation of webpage HTML file

### Install httpd (Apache server to host webpage)     
      yum install httpd -y

### Create webpage 
      cd /var/www/html/
      vim index.html
            Enter your content and save

      MAKE SURE THE NAME SHOULD ONLY BE "index.html" or else it'll not host and will consider httpd default page
      
![Capture](https://github.com/shubnimkar/Alpha-one/assets/46809421/b3ec29ac-12ff-44af-8468-493d7d976956)




## Windows Server 2016

Network Adapters : HOST-ONLY

#### Now configure IP for the same
      
      manual IP
      > Set IP : 10.10.10.143 (In same network as pfsense LAN IP)
      > Gateway : 10.10.10.140 (IP of Pfsense)
      > DNS : 192.168.100.2 (WAN IP of Pfsense to access the internet)

![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_13_27](https://github.com/shubnimkar/Alpha-one/assets/46809421/e884223e-aeed-4aa2-9727-71550de2db83)


#### Now configure webserver for the same

Open server manager to create a server:
Lets start:

* #### Step 1
  * Local Server 
  * Add roles and features
    
![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_37_57](https://github.com/shubnimkar/Alpha-one/assets/46809421/63c4cdc1-975c-442c-9bbb-9a63cebd2798)

* #### Step 2
  * Next
    
![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_38_11](https://github.com/shubnimkar/Alpha-one/assets/46809421/8e74889e-7995-4e71-aa1e-94184ccf057f)

* #### Step 3
  * Role based or feature based installation
  * Next

![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_38_16](https://github.com/shubnimkar/Alpha-one/assets/46809421/57b404ed-4f26-4d03-b6a1-eb079375e4d7)

* #### Step 4
  * Select from server pool
  * Next
    
![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_38_22](https://github.com/shubnimkar/Alpha-one/assets/46809421/119d8c53-49ef-4122-b73c-d87cb1d81c6b)

* #### Step 5
  * Select Web Server IIS from list
  * Next
    
![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_38_40](https://github.com/shubnimkar/Alpha-one/assets/46809421/778d90e8-1b60-43c7-a8eb-b89c9dda77c1)

* #### Step 6
  * Next
    
![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_38_50](https://github.com/shubnimkar/Alpha-one/assets/46809421/fa92c619-3fe0-4dc0-a01e-9cad82f770bd)

* #### Step 7
  * Install
    
![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_39_37](https://github.com/shubnimkar/Alpha-one/assets/46809421/8e2eef3f-bfd3-48b3-b57e-1581b309d1e2)

### Finally on server manager you can see the created server

![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_37_43](https://github.com/shubnimkar/Alpha-one/assets/46809421/749f3ce9-05c0-42bf-89a8-9f116338daf3)

### Create web page

* Go to C-Drive
  * search for inetpub
  * wwwroot
  * inetpub/wwwroot/  (This is path)
    
* Create a folder to store your html file
* Then create html file and enter the content as per your wish
  
![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_36_22](https://github.com/shubnimkar/Alpha-one/assets/46809421/1c868612-c6ca-47fc-bf87-c987047bf87a)


## Now configure the web server

* Go to server manager
  * Local server

* #### Step 1
  * IIS

![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_41_27](https://github.com/shubnimkar/Alpha-one/assets/46809421/d18ca46e-6334-42b7-b031-28d4f7ee9b90)

* #### Step 2
  * Internet information services manager (IIS)

![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_41_35](https://github.com/shubnimkar/Alpha-one/assets/46809421/21445a1d-9bbf-40cd-b4b3-1e0aed99dd38)
* #### Step 3
  * Right click on sites create new add path for file
    
![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_41_51](https://github.com/shubnimkar/Alpha-one/assets/46809421/5a72c21b-774a-48ee-98ea-6f3f05167f6a)

* #### Step 4
  * Bindings

![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_41_59](https://github.com/shubnimkar/Alpha-one/assets/46809421/c15fbcf3-1d26-4e07-bc15-bcdc6b3dcc2a)

* #### Step 5
  * Add IP and port number

![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_42_08](https://github.com/shubnimkar/Alpha-one/assets/46809421/92765f91-92d8-470b-aeec-5f7e419fbfef)

* #### Step 6
  * Close

![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_42_16](https://github.com/shubnimkar/Alpha-one/assets/46809421/0704aae4-7f14-4513-a4f9-c225b905eddd)



## Allow port 80 in Windows firewall 

* #### Step 1
  * Inbound rules
  * New rule
    
![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_44_23](https://github.com/shubnimkar/Alpha-one/assets/46809421/528153bd-0630-452d-a063-d116eec9fdad)

* #### Step 2
  * Port
  * Next
    
![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_44_34](https://github.com/shubnimkar/Alpha-one/assets/46809421/64cb2a18-6a2d-45bd-aa31-2bf8565bf40d)

* #### Step 3
  * Specific local ports
  * 80
  * next
    
![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_45_54](https://github.com/shubnimkar/Alpha-one/assets/46809421/3503497f-321c-4b36-b11f-306dacfa4f55)

* #### Step 4
  * Allow the connection
  * next
    
![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_45_59](https://github.com/shubnimkar/Alpha-one/assets/46809421/b5990f37-c2d5-497a-b89a-78760289b745)

* #### Step 5
  * Select all
  * next
    
![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_46_03](https://github.com/shubnimkar/Alpha-one/assets/46809421/8cdf95f3-6c03-44ae-b694-18ff253ec5cb)

* #### Step 6
  * Give name
  * finish
    
![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_46_15](https://github.com/shubnimkar/Alpha-one/assets/46809421/c7da048a-eb42-4396-a8b0-a0ba8db78cde)

### New rule added

![Windows Server 2016 (1) - VMware Workstation 30-06-2023 19_46_37](https://github.com/shubnimkar/Alpha-one/assets/46809421/e47b81b6-1347-4924-a675-f06f19ec8d37)


## Pfsense settings

#### Goto Firewall > NAT > Port forwarding

* #### HOME
* #### ADD

![pfSense home arpa - Firewall_ NAT_ Port Forward - Google Chrome 30-06-2023 19_50_46](https://github.com/shubnimkar/Alpha-one/assets/46809421/cc002d89-72a1-4fa0-81ba-6ebe7423a683)

#### Redirect target IP
#### Single Host and IP address of server 

![pfSense home arpa - Firewall_ NAT_ Port Forward - Google Chrome 30-06-2023 18_27_24](https://github.com/shubnimkar/Alpha-one/assets/46809421/3099ab6d-8a3d-4728-8c3f-526215df171f)

#### Redirect target PORT > HTTP

![pfSense home arpa - Firewall_ NAT_ Port Forward - Google Chrome 30-06-2023 18_27_42](https://github.com/shubnimkar/Alpha-one/assets/46809421/988088e4-8abf-47bf-bfba-bd5c0be8eeab)

#### Services > SNORT > Interface settings > WAN - RULES

#### Add custom rules for port forwarding

![pfSense home arpa - Services_ Snort_ Interface Settings_ WAN - Rules - Google Chrome 30-06-2023 09_48_11](https://github.com/shubnimkar/Alpha-one/assets/46809421/8a1bd27d-3591-4981-abb7-d92e50fbe31b)

#### Rules added

![pfSense home arpa - Firewall_ NAT_ Port Forward - Google Chrome 30-06-2023 18_27_04](https://github.com/shubnimkar/Alpha-one/assets/46809421/27085afe-c8b9-4f7e-a410-9d29db2f3fbd)


### Access both websites on the outer browser

#### Linux machine Webpage on port : 80

![192 168 100 160 - Google Chrome 30-06-2023 18_26_53](https://github.com/shubnimkar/Alpha-one/assets/46809421/7e0d3bcd-da78-4a22-a90a-6f6d654d60fd)

#### Windows Server Webpage on port : 8000

![192 168 100 160 - Google Chrome 30-06-2023 18_26_58](https://github.com/shubnimkar/Alpha-one/assets/46809421/415ed749-cc95-47a2-990e-999295df4283)
