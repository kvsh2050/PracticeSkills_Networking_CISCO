#  Networking Fundamentals with Cisco: Router, ASA Firewall & Packet Tracer

##  Introduction

In today's enterprise network infrastructure, security and routing are foundational components. As part of my hands-on networking skillset, I have implemented Cisco Routers and ASA Firewalls within **Cisco Packet Tracer**, Cisco's powerful network simulation tool. This project demonstrates not only my conceptual knowledge but also practical configuration capabilities, which are essential in roles like **Network Engineer**, **Cybersecurity Analyst**, or **Infrastructure Specialist**.


##  What is a Router?

A **router** is a layer 3 (network layer) device used to **route packets between different networks** based on their IP addresses. It:

- Maintains **routing tables**
- Supports **NAT (Network Address Translation)**
- Enables **inter-VLAN routing**
- Can provide **basic security functions**

###  Key Router Features
- IP Routing (Static and Dynamic)
- DHCP configuration
- Access Control Lists (ACLs)
- NAT/PAT for private to public IP translation


##  What is Cisco ASA Firewall?

**Cisco ASA (Adaptive Security Appliance)** is a security device that combines:

- **Firewall**
- **VPN concentrator**
- **Intrusion Prevention System (IPS)**

###  ASA Firewall Capabilities
- Stateful packet inspection
- Zone-based security
- Port and protocol filtering
- Site-to-Site & Remote Access VPNs



## 🛠 What is Cisco Packet Tracer?

**Cisco Packet Tracer** is a network simulation tool used to design, configure, and troubleshoot Cisco devices virtually. It's highly effective for learning and demonstrating:

- Router and Switch configuration
- ASA firewall setup
- End-to-end network design
- Troubleshooting scenarios



##  Implementation in Cisco Packet Tracer

###  1. Router Configuration
```plaintext
Router> enable
Router# configure terminal
Router(config)# interface GigabitEthernet0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# ip route 0.0.0.0 0.0.0.0 <Next-Hop-IP>
Router(config)# end
Router# write memory
````

### 🔐 2. ASA Firewall Configuration

```plaintext
ASA> enable
ASA# configure terminal
ASA(config)# interface ethernet0/0
ASA(config-if)# nameif outside
ASA(config-if)# security-level 0
ASA(config-if)# ip address <outside-IP> 255.255.255.0
ASA(config-if)# no shutdown
ASA(config-if)# exit

ASA(config)# interface ethernet0/1
ASA(config-if)# nameif inside
ASA(config-if)# security-level 100
ASA(config-if)# ip address <inside-IP> 255.255.255.0
ASA(config-if)# no shutdown
ASA(config-if)# exit

ASA(config)# access-list outside_access_in extended permit tcp any any eq 80
ASA(config)# access-group outside_access_in in interface outside
ASA(config)# route outside 0.0.0.0 0.0.0.0 <Next-Hop-IP>
ASA(config)# end
ASA# write memory
```

###  3. Connecting Router, ASA, and End Devices

1. **Connect Router to ASA (outside interface)**
2. **Connect ASA (inside interface) to switch**
3. **Connect end devices (PCs/Servers) to switch**
4. **Set static/default route on router and ASA**
5. **Assign IPs to devices and test connectivity using ping**



## Outcomes and Skills Demonstrated

*  Routing and switching fundamentals
*  Firewall deployment and access control
*  Hands-on with Cisco CLI and GUI
*  Network troubleshooting and logical topology design
*  Real-world use-case simulation using Packet Tracer


## 🖼️ Project Demonstration

Below are the screenshots from my implementation in Cisco Packet Tracer:

![Screenshot 2024-04-05 125647](https://github.com/user-attachments/assets/911fafd2-cb43-4249-a4c7-4d2263f76987)
![Screenshot 2024-04-08 093814](https://github.com/user-attachments/assets/826803e4-4d12-4332-a2c4-857c0345941f)
![Screenshot 2024-04-08 145635](https://github.com/user-attachments/assets/327d307a-1ba9-4021-b9df-82f0948e20e9)
![Screenshot 2024-04-10 181352](https://github.com/user-attachments/assets/894868b6-66a9-4e4b-a2a1-23b50ba6bf60)
![Screenshot 2024-04-11 181335](https://github.com/user-attachments/assets/dfd65c93-9d94-43f8-92a0-d8185c526359)
![Screenshot 2024-04-17 172138](https://github.com/user-attachments/assets/0e040e12-c142-40a2-889a-42806c1e1d02)
![Screenshot 2024-04-17 172218](https://github.com/user-attachments/assets/e118a430-e258-4243-8f05-7aef7e71ca29)
![Screenshot 2024-04-17 172321](https://github.com/user-attachments/assets/53871e74-1fe6-4dd0-89a6-2b24edd136d2)
![Screenshot 2024-04-17 172335](https://github.com/user-attachments/assets/de424224-b65b-4ecc-b670-ce2958fe931c)
![Screenshot 2024-04-17 172345](https://github.com/user-attachments/assets/a8d88324-ddf2-48db-8e1a-058a9c783fa6)


> *Note: These images show real CLI outputs and topology snapshots from my Packet Tracer simulation.*
