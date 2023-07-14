Q1. Implement firewall rules using iptables to secure a Linux server that hosts a website with a public [P 1961.113.45.
a. Write a set of iptables rules to allow SSH traffic from IP 196.1.113.4 only.
b. Write a set of iptables rules to allow incoming HTTP (port 80) and HTTPS (port 443) traffic to the web server.
c. Write a set of iptables rules to log packets directed to port 22.
    
    Step 3: Install `iptables`:
    - CentOS 7 uses `firewalld` as the default firewall management tool. To switch to `iptables`, we need to disable and remove `firewalld`:
          ```
          systemctl stop firewalld
          systemctl disable firewalld
          yum remove firewalld
          ```
    
    - Install `iptables` using the following command:
          ```
          yum install iptables-services
          ```
        
    - Enable `iptables` to start on system boot:
          ```
          systemctl enable iptables
          ```
    
    Step 4: Configure firewall rules using `iptables`:
    - Start by flushing existing `iptables` rules:
          ```
          iptables -F
          iptables -X
          iptables -Z
          ```
    
    - Set the default policy to deny all incoming connections and allow all outgoing connections:
          ```
          iptables -P INPUT DROP
          iptables -P FORWARD DROP
          iptables -P OUTPUT ACCEPT
          ```
    
    - Allow incoming SSH traffic from the IP address 196.1.113.4 only:
          ```
          iptables -A INPUT -p tcp --dport 22 -s 196.1.113.4 -j ACCEPT
          iptables -A INPUT -p tcp --dport 22 -j DROP
          ```
    
    - Allow incoming HTTP (port 80) and HTTPS (port 443) traffic for your website:
          ```
          iptables -A INPUT -p tcp --dport 80 -j ACCEPT
          iptables -A INPUT -p tcp --dport 443 -j ACCEPT
          ```
        
    - Log packets directed to port 22 (SSH):
          ```
          iptables -A INPUT -p tcp --dport 22 -j LOG --log-prefix "SSH Packet: "
          ```
    
    - Save the `iptables` rules to persist across reboots:
          ```
          service iptables save
          ```
    
    Step 5: Test the configuration:
    - Restart the `iptables` service to apply the new rules:
          ```
          systemctl restart iptables
          ```
    
    - Ensure that SSH traffic is allowed only from the IP address 196.1.113.4, and incoming HTTP (port 80) and HTTPS (port 443) traffic is permitted for your website. Additionally, 
    packets directed to port 22 should be logged.
    
    That's it! You have now installed `iptables` on your CentOS 7 VM and configured firewall rules to secure your server hosting a website with a public IP address 1961.113.45.



Q2. Configure Squid as a proxy server to allow only web browsing for the IP subnet 192.168.40.0/24. It should only allow access to websites from the *.gov.in domain

    Certainly! Here's a step-by-step guide, starting from the installation of Squid proxy server on your CentOS 7 VM, to the configuration that allows only web browsing
    for the IP subnet 192.168.40.0/24 and restricts access to websites from the *.gov.in domain:
    
    Step 1: Install Squid on CentOS 7:
    - Log in to your CentOS 7 VM as the root user or a user with sudo privileges.
    - Update the system packages using the following command:
            ```
            yum update
            ```
    - Install Squid using the following command:
            ```
            yum install squid
            ```
    
    Step 2: Configure Squid proxy server:
    - Open the Squid configuration file for editing:
            ```
            nano /etc/squid/squid.conf
            ```
    
    - Locate the `http_access` section and add the following lines:
            ```
            acl localnet src 192.168.40.0/24
            http_access allow localnet
            ```
      These lines define an access control list (ACL) for the IP subnet 192.168.40.0/24 and allow access only to the defined subnet.
    
    - Next, add the following lines to allow access to websites from the *.gov.in domain:
            ```
            acl govin_domains dstdomain .gov.in
            http_access allow govin_domains
            ```
      These lines define an ACL for the *.gov.in domain and allow access only to websites within that domain.
    
    - Save the changes and exit the editor (Ctrl+X, then Y).
    
    Step 3: Start and enable Squid:
    - Start the Squid service:
            ```
            systemctl start squid
            ```
          
    - Enable Squid to start on system boot:
            ```
            systemctl enable squid
            ```
          
    Step 4: Configure client devices:
    - On the client devices within the 192.168.40.0/24 subnet, configure the web browser's proxy settings to point to the Squid proxy server on the appropriate port (default is 3128).
    
    Step 5: Test the configuration:
    - Open a web browser on a client device within the 192.168.40.0/24 subnet and try accessing a website from the *.gov.in domain. It should be accessible.
    - Try accessing websites from other domains. They should be blocked.
    
    That's it! You have now installed Squid proxy server on your CentOS 7 VM and configured it to allow only web browsing for the IP subnet 192.168.40.0/24,
    while restricting access to websites from the *.gov.in domain.


Q3 Generate alerts using Snort on a Linux VM or pfSense for any connection attempts on port 22 for the server at IP address 196.1.113.45, except those from IP 196.1.113.4.  

    To generate alerts using Snort on a CentOS 7 Linux VM for any connection attempts on port 22 for the server at IP address 196.1.113.45, except those from IP 196.1.113.4, 
    you can follow these steps:
    
    Step 1: Install Snort on CentOS 7:
    - Log in to your CentOS 7 VM as the root user or a user with sudo privileges.
    - Update the system packages using the following command:
            ```
            yum update
            ```
    - Install Snort using the following command:
            ```
            yum install epel-release
            yum install snort
            ```
    
    Step 2: Configure Snort rules:
    - Open the Snort configuration file for editing:
            ```
            nano /etc/snort/snort.conf
            ```
          
    - Locate the section that begins with `# Define your network addresses`, and add the following lines:
            ```
            ipvar HOME_NET any
            ipvar EXTERNAL_NET any
            ```
    
    - Locate the section that begins with `# Define your dynamic DNS domains`, and add the following line:
            ```
            ipvar DNS_SERVERS $HOME_NET
            ```
    
    - Scroll down to the section that begins with `# Set up the external network addresses. Leave as "any" in most situations`, and add the following line:
            ```
            include $RULE_PATH/local.rules
            ```
    
    - Save the changes and exit the editor (Ctrl+X, then Y).
    
    Step 3: Create a local.rules file:
    - Create the local.rules file using the following command:
            ```
            nano /etc/snort/rules/local.rules
            ```
    
    - Add the following rule to allow connections from IP 196.1.113.4 on port 22:
            ```
            pass tcp any any -> 196.1.113.45 22 (msg:"Allow SSH from IP 196.1.113.4"; sid:1000001; rev:1;)
            ```
    
    - Add the following rule to generate alerts for connection attempts on port 22 from any IP except 196.1.113.4:
            ```
            alert tcp any any -> 196.1.113.45 22 (msg:"Connection attempt to SSH port"; sid:1000002; rev:1;)
            ```
          
    - Save the changes and exit the editor (Ctrl+X, then Y).
    
    Step 4: Start Snort in alert mode:
    - Start Snort in alert mode using the following command:
            ```
            snort -A alert -c /etc/snort/snort.conf -i <interface>
            ```
      Replace `<interface>` with the appropriate network interface name (e.g., eth0).
    
    - Snort will now monitor network traffic on port 22 and generate alerts for connection attempts to the server at IP address 196.1.113.45, except for those from IP 196.1.113.4.
    
    That's it! You have now installed Snort on your CentOS 7 VM and configured it to generate alerts for connection attempts on port 22 for the server at IP address 196.1.113.45, 
    except those from IP 196.1.113.4.


Q3. Solution for pfsense

      Certainly! Here's a detailed guide on how to generate alerts using Snort on pfSense for any connection attempts on port 22 for the server at IP address 196.1.113.45, 
      except those from IP 196.1.113.4:
      
      Step 1: Install and Configure pfSense:
          - Download the pfSense ISO image from the official pfSense website (https://www.pfsense.org/download/).
          - Create a new virtual machine using your preferred virtualization software (e.g., VirtualBox, VMware).
          - Mount the pfSense ISO image and start the virtual machine.
          - Follow the on-screen instructions to install and configure pfSense.
      
      Step 2: Install the Snort Package:
          - Log in to the pfSense web interface.
          - Navigate to "System" -> "Package Manager" -> "Available Packages".
          - Search for "snort" and click on the "Install" button next to the Snort package to install it.
      
      Step 3: Configure Snort on pfSense:
          - Once the Snort package is installed, go to "Services" -> "Snort" to access the Snort configuration page.
          - Click on the "Global Settings" tab and configure the necessary settings (e.g., select the network interface, enable promiscuous mode).
          - Go to the "Updates" tab and click on "Update Rules" to download the latest Snort rules.
          - After the rules update is complete, go to the "Categories" tab and select the desired rule categories for monitoring.
          - Next, go to the "Preprocessors" tab and enable any desired preprocessors for additional network analysis (optional).
          - Click on the "Save" button to apply the configuration.
      
      Step 4: Create Snort Rules:
          - Go to the "RULES" tab in the Snort configuration page.
          - Click on the "Add" button to create a new Snort rule.
          - In the "SID Mgmt" field, enter a unique ID for the rule (e.g., 1000001).
          - In the "Description" field, provide a meaningful description for the rule (e.g., "Allow SSH from IP 196.1.113.4").
          - In the "Action" field, select "Pass" from the drop-down menu.
          - In the "Source IP" field, enter "196.1.113.4".
          - In the "Destination IP" field, enter "196.1.113.45".
          - In the "Destination Port" field, enter "22".
          - Click on the "Save" button to save the rule.
      
          - Click on the "Add" button again to create another Snort rule.
          - In the "SID Mgmt" field, enter a unique ID for the rule (e.g., 1000002).
          - In the "Description" field, provide a meaningful description for the rule (e.g., "Connection attempt to SSH port").
          - In the "Action" field, select "Alert" from the drop-down menu.
          - In the "Source IP" field, enter "any".
          - In the "Destination IP" field, enter "196.1.113.45".
          - In the "Destination Port" field, enter "22".
          - Click on the "Save" button to save the rule.
      
      Step 5: Start Snort and Monitor Alerts:
          - On the Snort configuration page, go to the "INTERFACE SETTINGS" tab.
          - Select the desired network interface from the "Interface" drop-down menu.
          - Scroll down and click on the "Save" button to apply the changes.
          - On the same page, scroll back up and click on the "Start" button to start Snort.
      
      - Snort is now monitoring network traffic on port 22 and generating alerts for connection attempts to the server at IP address 196.1.113.45, except for those 
      from IP 196.1.113.4.
      
      Step 6: View Snort Alerts:
          - To view Snort alerts, go to the "Alerts" tab in the Snort configuration page.
          - You will see a list of generated alerts, including details such as the timestamp, source IP, destination IP, and description.
      
      That's it! You have now installed Snort on pfSense and configured it to generate alerts for connection attempts on port 22 for the server at IP address 196.1.113.45,
      except those from IP 196.1.113.4.


Q4. Set up a high-availability architecture for a web application using Nginx as a reverse proxy server. Configure Nginx to act as a reverse proxy and distribute 
incoming traffic across multiple servers using round-robin load balancing.

    To set up a high-availability architecture for a web application using Nginx as a reverse proxy server with round-robin load balancing, here's a detailed solution from installation to the final answer for your CentOS 7 VMs:
    
    Step 1: Install Nginx on CentOS 7 VMs:
    - Log in to each CentOS 7 VM as the root user or a user with sudo privileges.
    - Update the system packages using the following command:
          ```
          yum update
          ```
    - Install Nginx using the following command:
          ```
          yum install nginx
          ```
    
    Step 2: Configure Nginx as a Reverse Proxy with Round-Robin Load Balancing:
    - Open the Nginx configuration file for editing:
          ```
          nano /etc/nginx/nginx.conf
          ```
    - Within the `http` block, locate the `server` block and remove the default configuration.
    - Configure Nginx as a reverse proxy with round-robin load balancing by adding the following lines inside the `http` block:
          ```
          upstream backend {
            server <IP_ADDRESS_1>;
            server <IP_ADDRESS_2>;
            # Add more server entries as needed
          }
          server {
            listen 80;
            location / {
              proxy_pass http://backend;
              proxy_set_header Host $host;
              proxy_set_header X-Real-IP $remote_addr;
            }
          }
          ```
      Replace `<IP_ADDRESS_1>` and `<IP_ADDRESS_2>` with the actual IP addresses of your backend servers.
    
    - Save the changes and exit the editor (Ctrl+X, then Y).
    
    Step 3: Start Nginx and Enable Auto-Start on Boot:
    - Start the Nginx service using the following command:
          ```
          systemctl start nginx
          ```
    
    - Enable Nginx to start on system boot:
          ```
          systemctl enable nginx
          ```
    
    Step 4: Configure Backend Servers:
    - Set up your backend servers (web servers) with your web application. Ensure the application is running on each server and listening on the appropriate port (e.g., port 80).
    
    Step 5: Test the High-Availability Architecture:
    - Access the public IP address of your CentOS 7 VM running Nginx in a web browser.
    - Nginx will act as a reverse proxy and distribute incoming traffic across the backend servers using round-robin load balancing.
    - Verify that requests are being distributed to each backend server in a round-robin manner.
    - Monitor the backend servers to confirm that they are receiving and responding to requests.
    
    That's it! You have now installed Nginx on your CentOS 7 VMs and configured it as a reverse proxy server with round-robin load balancing for your high-availability architecture.
    
