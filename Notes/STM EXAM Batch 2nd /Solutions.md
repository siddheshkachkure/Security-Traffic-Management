Q1.  Implement firewall rules using iptables to secure a Linux server that hosts a website with a public IP 1961.113.45.

    To implement firewall rules using `iptables` to secure a Linux server hosting a website with a public IP address of 1961.113.45, you can follow these steps:

    1. Connect to your Linux server via SSH or access its terminal.
    2. Open a terminal and execute the following commands as the root user or with sudo privileges.

    First, ensure that your firewall is set to deny all incoming connections by default:
        ```
        iptables -P INPUT DROP
        iptables -P FORWARD DROP
        iptables -P OUTPUT ACCEPT
        ```

    Allow incoming connections related to established connections:
        ```
        iptables -A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT
        ```

    Allow incoming SSH connections to manage your server (assuming SSH uses the default port 22):
        ```
         iptables -A INPUT -p tcp --dport 22 -j ACCEPT
        ```

    Allow incoming HTTP (port 80) and HTTPS (port 443) connections for your website:
        ```
        iptables -A INPUT -p tcp --dport 80 -j ACCEPT
        iptables -A INPUT -p tcp --dport 443 -j ACCEPT
        ```

    Allow ICMP (ping) requests (optional):
        ```
        iptables -A INPUT -p icmp -j ACCEPT
        ```

    If you want to restrict access to specific IP addresses or IP ranges, you can add additional rules. For example, to allow access only from a specific IP address (e.g., 192.168.1.100):
        ```
        iptables -A INPUT -p tcp -s 192.168.1.100 --dport 22 -j ACCEPT
        iptables -A INPUT -p tcp -s 192.168.1.100 --dport 80 -j ACCEPT
        iptables -A INPUT -p tcp -s 192.168.1.100 --dport 443 -j ACCEPT
        ```

Note: Replace `192.168.1.100` with the actual IP address or IP range you want to allow access from.

    Lastly, save the iptables rules so they persist across reboots:
        ```
        iptables-save > /etc/iptables/rules.v4  
        ```

    These rules provide a basic firewall configuration, allowing only essential incoming connections while blocking the rest. Make sure to adjust them according to your specific requirements.

Remember to test your website and any other services to ensure they are accessible as intended after applying the firewall rules.



Q1.a) Write a set of iptables rules to allow SSH traffic from IP 196.1.113.4 only.


  ```
  yum update
  ```

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
        
    Step 4: Configure `iptables` rules:
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
        
    - Allow incoming connections related to established connections:
          ```
          iptables -A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT
          ```
    
    - Allow incoming SSH traffic from the IP address 196.1.113.4:
          ```
          iptables -A INPUT -p tcp -s 196.1.113.4 --dport 22 -j ACCEPT
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
    
    - Ensure that you have access to SSH from the IP address 196.1.113.4, while other connections are blocked.

    That's it! You have now installed CentOS 7 on a virtual machine, installed `iptables`, and configured firewall rules to allow SSH traffic only from the IP address 196.1.113.4.



Q1.b  Write a set of iptables rules to allow incoming HTTP (port 80) and HTTPS (port 443) traffic to the web server.
    

    Step 1: Install `iptables`:
    - Log in to your CentOS 7 VM as the root user or a user with sudo privileges.
    - Update the system packages using the following command:
          ```
          yum update
          ```
    - Install `iptables` using the following command:
          ```
          yum install iptables-services
          ```
    - Enable `iptables` to start on system boot:
          ```
          systemctl enable iptables
          ```
    
    Step 2: Configure `iptables` rules:
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
    - Allow incoming connections related to established connections:
          ```
          iptables -A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT
          ```
    - Allow incoming HTTP (port 80) and HTTPS (port 443) traffic to your web server:
          ```
          iptables -A INPUT -p tcp --dport 80 -j ACCEPT
          iptables -A INPUT -p tcp --dport 443 -j ACCEPT
          ```
    - Save the `iptables` rules to persist across reboots:
          ```
          service iptables save
          ```
    
    Step 3: Test the configuration:
    - Restart the `iptables` service to apply the new rules:
          ```
          systemctl restart iptables
          ```
        
    - Verify that your web server can now receive incoming HTTP and HTTPS traffic on ports 80 and 443, respectively.
    
    That's it! You have now installed `iptables` on your CentOS 7 VM and configured firewall rules to allow incoming HTTP (port 80) and HTTPS (port 443) traffic to your web server.


Q1.c Write a set of iptables rules to log packets directed to port 22.
