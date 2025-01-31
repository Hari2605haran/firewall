# Build and Configure a Firewall in Linux

## 📌 Project Overview
This project demonstrates the process of building and configuring a firewall on a Linux system to enhance network security. It covers firewall rule implementation, packet filtering, and access control using **iptables** and **ufw (Uncomplicated Firewall)**.

## 🚀 Features
- Packet filtering and traffic control
- Custom firewall rules using **iptables**
- Simple firewall management with **ufw**
- Logging and monitoring network traffic
- Preventing unauthorized access
- Allowing/Denying specific IPs and ports

## 🛠 Technologies Used
- **Linux (Ubuntu, Debian, or CentOS)**
- **iptables** – Advanced firewall rule management
- **ufw** – Simplified firewall configuration tool
- **Bash Scripting** – Automating firewall setup
- **netfilter** – Kernel-level packet filtering

## 📂 Project Structure
```
├── firewall-setup.sh   # Bash script to configure iptables
├── ufw-rules.txt       # Sample UFW rules
├── README.md           # Project documentation
└── logs/               # Firewall logs (if enabled)
```

## 🔧 Installation & Usage
### Prerequisites
Ensure you have a Linux system with administrative privileges.

### Setup Instructions
1. Clone this repository:
   ```bash
   git clone https://github.com/Hari2605haran/firewall-project.git
   cd firewall-project
   ```
2. Grant execution permission to the script:
   ```bash
   chmod +x firewall-setup.sh
   ```
3. Run the script to configure the firewall:
   ```bash
   sudo ./firewall-setup.sh
   ```
4. For UFW-based setup, enable UFW and apply rules:
   ```bash
   sudo ufw enable
   sudo ufw allow 22/tcp   # Example: Allow SSH
   sudo ufw status verbose
   ```

## 🔍 Firewall Rules Examples
### iptables
```bash
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT  # Allow SSH
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT  # Allow HTTP
sudo iptables -A INPUT -p tcp --dport 443 -j ACCEPT # Allow HTTPS
sudo iptables -A INPUT -j DROP                      # Drop all other traffic
```
### UFW
```bash
sudo ufw allow 22/tcp   # Allow SSH
sudo ufw allow 80/tcp   # Allow HTTP
sudo ufw allow 443/tcp  # Allow HTTPS
sudo ufw deny 3306/tcp  # Deny MySQL remote access
```

## 📖 Logs & Monitoring
To check iptables logs:
```bash
sudo tail -f /var/log/syslog | grep "iptables"
```
To check UFW logs:
```bash
sudo less /var/log/ufw.log
```

## 📜 License
This project is licensed under the **MIT License**.

## 🤝 Contributing
Contributions are welcome! Feel free to fork this repository and submit a pull request.

## 📧 Contact
For queries, feel free to reach out:
- **GitHub:** [https://github.com/Hari2605haran]
- **Email:** harisudhanbv@example.com
