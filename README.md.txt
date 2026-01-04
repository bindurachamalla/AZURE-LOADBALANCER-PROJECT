AZURE PROJECT : WEB & APP DEPLOYMENT WITH LOAD BALANCERS
Submitted by:
Rachamalla Bindu

Objective :
● Create Azure resources (RG, VNet, subnets)
● Deploy two Linux VMs named web and app
● Configure NSGs to allow ports 22, 80 (both VMs) and 8080 (app VM)
● Install Nginx on web, Tomcat on app
● Deploy Public Load Balancer for Web (HTTP) and Private Load Balancer for App
(8080)
● Verify end-to-end connectivity

Abstract :
● Deploy an Azure Resource Group containing a VNet with two subnets, two VMs
(Web and App), Security Rules allowing SSH(22), HTTP(80), and App(8080).
● Install Nginx on Web VM and Tomcat on App VM. 
● Create a public load balancer for the Web tier (port 80) and an internal/private load
balancer for the App tier (port 8080). 
● Verify connectivity by accessing public LB IP and confirming Nginx can reach the
App through the private LB. 

⮚ 1. Create a Resource group :
⮚ 2. Create a Virtual Network with Two Subnets :
● Subnet 1 : WEBsubnet
● Subnet2 : Appsubnet

⮚ 3.Create WEB Virtual Machine :

● OS: Linux (Ubuntu)
● Subnet: Web Subnet
● Public IP: Yes (for SSH access)
● Allow public inbound rules HTTP (80), SSH (22)

● Here the WEBvm is created in virtual network in web subnet. 

⮚ 4. Install NGINX on Web VM :

● By using below commands install nginx in mobaxtrem
● Sudo su (to switch to root user)
● sudo apt update
● sudo apt install nginx –y
● sudo systemctl start nginx

● The successful installation of NGINX was verified by checking the service status using
the systemctl command, which showed the service as active and running in the above
image.

⮚ 5. Verify NGINX :

● Browse Web VM public IP
● NGINX default page should be displayed

⮚ 6. Create Application Virtual Machine (App VM) :

● OS: Linux (Ubuntu)
● Subnet: App Subnet
● Public IP: Optional (recommended only for admin access)

● Allow inbound rules SSH (22)

⮚ 7. Install Tomcat on App VM :

By using below commands install Tomcat in mobaxterm :
● Sudo su (to switch to root user)
● sudo apt update
● sudo apt install openjdk-11-jdk –y
● wget https://dlcdn.apache.org/tomcat/tomcat-10/v10.1.50/bin/apache-tomcat- 10.1.50.tar.gz
● tar -xvzf apache-tomcat-10.1.50.tar.gz
● mv apache-tomcat-10.1.50 tomcat
● ls
● cd /opt/tomcat/bin
● ./startup.sh

⮚ Apache Tomcat was successfully installed and started, and the default Tomcat welcome
page was verified by accessing it via the VM public IP on port 8080.

⮚ 8. Create Azure Public Load Balancer :

A. Select standard load balancer and Create .
● Now in type select Public because it is public load balancer.
B. Frontend IP Configuration .
C. Backend Pool: Add Web VM . 
D. Health Probe :
● Protocol: TCP
● Port: 80
E. Load Balancing Rule:
● Frontend Port: 80
● Backend Port: 80
● Backend Pool: Web VM

⮚ 9. Create Azure Private Load Balancer :

A. Create Private Load Balancer
Here in type select internal because it is private load balancer . 
B. Frontend IP Configuration:
● Private IP from AppSubnet
C. Backend Pool : Add App VM
D. Health Probe:
● Protocol: TCP
● Port: 8080
E. Load Balancing Rule:
● Frontend Port: 8080
● Backend Port: 8080
● Backend Pool: App VM

⮚ 10. Connectivity Testing (Main Validation Step) :

● Test connection from Web VM to Private Load Balancer
● Connect to Web VM using SSH
● With WEB virtual machine public Ip and username. 
● Run telnet command.
 
This confirms:
● Traffic flows from the public load balancer to the web VM and that Nginx can reach
Tomcat via the private load balancer. 

⮚ Security Validation :

● Tomcat is not exposed publicly. 
● Only Private Load Balancer IP is accessible from Web VM. 
● Application layer is protected inside the VNet. 
● End users cannot directly access Tomcat from the internet. 
● This prevents unauthorized external access to the application layer. 
● External traffic cannot reach the Private Load Balancer. 
● Only the Web VM (NGINX) is exposed through the Public Load Balancer. 
● Backend Application services remain isolated from the internet . 

⮚ Conclusion:

● In this project, we successfully implemented Azure Public and Private Load Balancers
to design a secure two-tier architecture. The Public Load Balancer exposes the Web
layer (NGINX) to the internet, while the Private Load Balancer ensures secure
internal communication with the Application layer (Tomcat). 
● Connectivity was validated using telnet, confirming proper backend pool
configuration and network security. This architecture follows real-time industry best
practices for scalability, security, and high availability.
