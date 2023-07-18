#  IPTABLES
  
    [root@STM1 ~]# yum install iptables-services iptables-utils
    iptables -L

# FIREWALLD

    ## To block icmp on network:
      firewall-cmd --zone=public --add-rich-rule 'rule family="ipv4" source address="0.0.0.0/0" protocol value="icmp" reject '
    
    ## To allow http traffic:
      
      install httpd
      cd /var/www/html/
      isme jake index.html banao
    
          firewall-cmd --zone=public --remove-service=https
          firewall-cmd --zone=public --remove-service=http
    
      aur sida bahar k browser pe jake ip se access karo machine NAT pe rakhna pehele dikao ki access nahi hai upar k rule       daal kar
    
      aur phr niche ka dalo aur access karke dikhao
      
          firewall-cmd --zone=public --add-service=https
          firewall-cmd --zone=public --add-service=http
    ## allow  SSH from any ip
        firewall-cmd  --zone=private --add-rich-rule='rule family="ipv4" source address="192.168.1.0/24" service name="ssh" accept'
    
    ## Commands
        sudo firewall-cmd --get-zones
        sudo firewall-cmd --get-active-zones
        sudo firewall-cmd --change-zone=public
        sudo firewall-cmd --get-services
        sudo firewall-cmd --list-services
        sudo firewall-cmd --zone=public --list-ports
        sudo firewall-cmd --add-port=8065/tcp
    
# PFSENSE
    PFSENSE MACHINE
    1 CENTOS & 1 WINDOWS
    SIDHA IP BASED RULE DAALO IP BLOCK KARNE
# WIRESHARK

    FOR ICMP PACKAGES 
    SIDHA KALI K IP KO PING KARNA AUR PEHELE WIRESHARK CHALU KAR DENA ICMP PACKS AYEGA SCREENSHOT LEKE DAAL DO
    
    FOR WEBSERVER
    KALI ME FOLDER BANAO INDEX.HTML BANAO
    sudo python3 -m http.server 8001
    YE SCRIPT CHALA DO AUR BS WIRESHARK CHALA DO

# SNORT (ALERT)
    alert tcp any any -> any 8010 (msg:"virus.py downloaded";content:"virus.py";sid:1000001;rev:1;)
    alert tcp any 8010 -> any any (msg:"Hackers website accessed";content:"Hackers website";sid:1000002;rev:1;)
    just check in alerts

    for packet of more size here >256
    alert icmp any any -> 192.168.100.156 any (msg:"Large packet detected";dsize:>256;sid:1000003;rev:1;)
    ping -l 512 192.168.100.156

    for ttl <3
    alert icmp $HOME_NET any -> any any (msg:"Trace Route detected";ttl:<3;sid:1000004;rev:1;)

    for nmap
    rule : alert tcp any any -> 192.168.100.156 any (msg:"Possible NMAP SCAN";flow:stateless;flags:S;sid:1000005;rev:1;)
    nmap -sS 192.168.100.155(pfsense nat)

    port forwarding for SSH
    and for alert :alert tcp 192.168.100.156 any -> 10.10.10.25 22 (msg:"SSH Access";sid:1000006;rev:1;)

    port forwarding
    1 centos & 1 windows
    cd /var/www/html/
    vim index.html
        Enter your content and save
    windows me bhi ek site

    Goto Firewall > NAT > Port forwarding
    

# SQUID
  
    1-MASTER CENTOS NAT&HO
    
    2- CLIENTS : CENTOS & WINDOWS HO
    
    ADD PROXY IN BROWSER (PFSENSE KA HO ADDRESS)
  
    MASTER
    
        yum install squid -y
        cd /etc/squid/squid.conf
        cache_dir ufs /var/spool/squid 128 16 256
        visible_hostname "apna naam dalo"
        squid -z
  
    conf file
  
        acl hpcsalab src 10.10.10.0/24
        acl microsoft dstdomain .microsoft.com
        http_access deny microsoft hpcsalab
        http_access allow hpcsalab
  
        acl blocked_sites dstdomain "/etc/squid/blocked-sites.txt"
                http_access deny blocked_sites hpcsalab
  
        acl my-time time A 18:00-20:00
                acl cdac dstdomain .bookmyshow.com
                http_access deny my-time
  [FOR USER WALA ](https://github.com/shubnimkar/Security-and-Traffic-Management/blob/master/Tutorials/Squid%20in%20RHEL-CENTOS.md#squid-authentication)

# SQUID PROXY

     PackageProxy Server: General SettingsGeneral

# OPENVPN
2 centos
master NAT,HO
client NAT
1 windows HO
# NGINX
# LOADBALANCER
    include /etc/nginx/conf.d/*.conf;
    
    upstream hpcsa {
    server 10.10.10.129 weight=3;
    server 10.10.10.132;
    }
    server {


    upstream test{
    	server 10.10.10.132:8000;
    	server 10.10.10.132:10000;
    	}	
    	
    	upstream test2{
    	server 10.10.10.132:9500;
    	server 10.10.10.132:10100;
    	}
# (REVERSE PROXY)
location / {
	proxy_pass http://localhost/;
}
location /linux {
	proxy_pass http://10.10.10.129/;
}
location /windows {
	proxy_pass http://10.10.10.132/;
}
