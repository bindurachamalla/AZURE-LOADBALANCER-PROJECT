# AZURE LOAD BALANCER PROJECT

## 📌 Project Overview
This project demonstrates the implementation of Azure Public and Private Load Balancers using a secure two-tier architecture in Microsoft Azure.  
The Web layer uses Nginx, and the Application layer uses Tomcat, protected using Network Security Groups and Private Load Balancer.

---

## 🧱 Architecture Components
- Resource Group  
- Virtual Network  
- Subnets (Web & App)  
- Network Security Groups  
- Public Load Balancer  
- Private Load Balancer  
- Web VM (Nginx)  
- App VM (Tomcat)  

---

## 📂 Resource Group
![Resource Group](images/RG.png)

---

## 🌐 Virtual Network
![VNet](images/Vnet.png)

---

## 🧩 Subnets
![Subnets](images/subnets.png)

---

## 🖥️ App Virtual Machine (Tomcat)
![App VM](images/appVM.png)

### 🔒 App NSG Configuration
![NSG for App](images/NSG_APP.png)

### ⚙️ Tomcat Installation
![Tomcat Installed](images/tomcat_installed.png)
![Tomcat Page](images/tomcat_page1.png)

---

## 🖥️ Web Virtual Machine (Nginx)
![Web VM](images/webVM.png)

### 🔑 Nginx Commands
![Nginx Commands](images/Nginx_commands.png)

### 🌐 Nginx Homepage
![Nginx Homepage](images/nginx-homepage.png)
![Nginx Page](images/nginx_page.png)

---

## 🌍 Public Load Balancer
![Public LB](images/publicLB.png)

### Frontend IP
![Public LB FE IP](images/pubLB-FEip.png)

### Backend Pool
![Public LB Backend Pool](images/pubLB-Bpool.png)

### Health Probe
![Public LB Health Probe](images/pubLB-HP.png)

### Load Balancing Rule
![Public LB Rule](images/pubLBrule.png)

---

## 🔒 Private Load Balancer
![Private LB](images/pvtLB.png)

### Frontend IP
![Private LB FE IP](images/pvtLB-FEIP.png)

### Backend Pool
![Private LB Backend Pool](images/pvtLB-Bpool.png)

### Health Probe
![Private LB Health Probe](images/pvtLB-HP.png)

### Load Balancing Rule
![Private LB Rule](images/pvtLB-rule.png)

---

## ⚖️ Load Balancers Overview
![Two Load Balancers](images/2LBs.png)

---

## 🌐 Web IP Verification
![Web IP](images/WEB-ip-copy.png)

---

## 🔌 Connectivity Test (Final Validation)
![Telnet Test](images/Telnet.png)

---

## ✅ Conclusion
This project demonstrates hands-on experience in:
- Azure Virtual Networks & Subnets  
- Network Security Groups (NSG)  
- Public and Private Load Balancers  
- Web and Application VM deployment  
- Secure internal application connectivity  

This implementation follows real-time industry best practices for security, scalability, and high availability.


Created by: Bindu Rachamalla  
Role: Azure / Cloud Fresher
