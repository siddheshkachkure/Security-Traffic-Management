To check if you have firewalld fired up, you run:

	# systemctl status firewalld

To get a "short answer" -- running / not running, run:

	# firewall-cmd --state
        or
    #systemctl status firewalld
To get services

    #firewall-cmd get-services

To start the firewall:

	# systemctl start firewalld

To stop the firewall:

	# systemctl stop firewalld
	
To make firewalld start on every server boot:
	
	# systemctl enable firewalld

Disable autostart:

	# systemctl disable firewalld
		

To list all the zones preconfigured:

	# firewall-cmd --get-zones

To list the active zone:

	# firewall-cmd --get-active-zones
	
_________________________________________
USEFUL COMMANDS:

To block all the traffic on the system: 

	# firewall-cmd --panic-on

To turn off the panic mode:

	# firewall-cmd --panic-off

To ask if the panic mode is enabled or not:

	# firewall-cmd --query-panic

Reload all the firewall rules without cutting off current connections:

	# firewall-cmd --reload

Reload all the firewall rules and cutt off all the current connections, use:

	# firewall-cmd --complete-reload
_________________________________________

To list all the available services:

	# firewall-cmd --get-services

To allow the conventional HTTP traffic, for interfaces in our "public" zone:

	# sudo firewall-cmd --zone=public --add-service=http

You can leave out the --zone= if you wish to modify the default zone. 

To verify the operation was successful, use the --list-all or --list-services operations:

	# firewall-cmd --zone=public --list-services

To make the "public" zone change permanent we type:
	
    # sudo firewall-cmd --zone=public --permanent --add-service=http

You can verify that this was successful by adding the --permanent flag to the --list-services operation. 

	# sudo firewall-cmd --zone=public --permanent --list-services

If our application runs on port 8080 and uses TCP, we could add this to the "public" zone for this session using the --add-port= parameter. Protocols can be either tcp or udp:

	# sudo firewall-cmd --zone=public --add-port=8080/tcp

We can verify that this was successful using the --list-ports operation:

	# firewall-cmd --list-ports
