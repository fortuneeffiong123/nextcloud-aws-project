# nextcloud-aws-project
Nextcloud self-hosted cloud storage on AWS EC2 (Apache, MariaDB, PHP)
Nextcloud on AWS EC2 — Production-Ready Self-Hosted Cloud Storage
🏢 Project Overview

This project demonstrates the deployment of a secure, scalable, self-hosted cloud storage system using AWS EC2 Ubuntu, Apache, MariaDB, and Nextcloud.
It showcases real-world DevOps, Cloud Engineering, and System Administration skills, including server provisioning, database configuration, web server management, and application deployment.

🚀 Why Nextcloud 
This project originally started with OwnCloud but was migrated due to modern system constraints.

❌ OwnCloud Limitation
Incompatible with PHP 8.5 (modern Ubuntu environments)
Requires deprecated PHP versions (≤ 8.0 / 8.1)
Poor support for latest OS stacks

✅ Why Nextcloud Was Selected
Fully compatible with PHP 8.5+
Actively maintained open-source ecosystem
Enterprise-grade file synchronization platform
Rich plugin ecosystem (collaboration, chat, calendar, etc.)
Widely adopted in production environments globally

🏗️ System Architecture
Client Browser
     │
     ▼
AWS EC2 (Ubuntu Server)
     │
     ├── Apache Web Server
     │
     ├── PHP 8.5 Runtime
     │
     ├── Nextcloud Application
     │
     └── MariaDB Database
☁️ Cloud Infrastructure

Cloud Provider: AWS
Compute: EC2 Ubuntu Instance
Storage: EBS Root Volume (20GB+ recommended)
Network: Security Group (HTTP/SSH enabled)

⚙️ Technology Stack
Layer	Technology
Operating System	Ubuntu Linux
Web Server	Apache2
Backend Language	PHP 8.5
Database	MariaDB
Application	Nextcloud
Cloud Platform	AWS EC2

🔧 Key Features Implemented
✔ Full LAMP stack deployment (Linux, Apache, MariaDB, PHP)
✔ Secure database configuration with dedicated user access
✔ Web-based file storage system (Nextcloud)
✔ Apache virtual hosting support
✔ File permission hardening (www-data ownership)
✔ Modular PHP extension configuration
✔ Production-ready deployment structure

🧱 Installation Summary
1. System Update
sudo apt update && sudo apt upgrade -y
2. Apache Installation
sudo apt install apache2 -y
3. PHP & Extensions
sudo apt install php libapache2-mod-php php-mysql php-cli php-curl php-gd php-xml php-mbstring php-zip unzip -y
4. MariaDB Setup
sudo apt install mariadb-server mariadb-client -y

5. Database Configuration
CREATE DATABASE owncloud;
CREATE USER 'ownclouduser'@'localhost' IDENTIFIED BY 'StrongPassword';
GRANT ALL PRIVILEGES ON owncloud.* TO 'ownclouduser'@'localhost';
FLUSH PRIVILEGES;

6. Nextcloud Deployment
wget https://download.nextcloud.com/server/releases/latest.zip
unzip latest.zip
sudo mv nextcloud /var/www/html/
sudo chown -R www-data:www-data /var/www/html/nextcloud

7. Apache Configuration
sudo a2enmod rewrite headers env dir mime
sudo systemctl restart apache2

🌐 Access Information
http://<EC2-PUBLIC-IP>/nextcloud


🔐 Security Practices Implemented
Database user isolation (no root DB access)
File permission hardening (www-data ownership)
Firewall-ready architecture (port 80/22 only)
Modular Apache configuration
Separation of application and system directories

📊 DevOps & Cloud Skills Demonstrated
This project demonstrates:

🟢 Cloud Infrastructure
AWS EC2 provisioning
Security group configuration
Linux server management

🟢 DevOps Engineering
LAMP stack deployment
Service configuration (Apache/MariaDB)
Package management and dependency resolution

🟢 Backend & Database
Relational database design (MariaDB)
User privilege management
Secure credential handling

🟢 System Administration
Linux permissions and ownership
Service monitoring and restart handling
Package troubleshooting and debugging

⚠️ Challenges Solved
1. PHP Version Incompatibility
Resolved by migrating from OwnCloud → Nextcloud
2. Temporary Filesystem Limit
Fixed by avoiding /tmp extraction
3. Dependency Conflicts
Resolved missing packages (bzip2, unzip)

🚀 Future Improvements
HTTPS encryption via Let’s Encrypt SSL
Domain name integration
Redis caching for performance
Automated backups (cron + S3)
Docker containerization
CI/CD deployment pipeline

👨‍💻 Author
Fortune Effiong

Junior Cloud & DevOps Enthusiast
AWS | Linux | System Administration | Backend Infrastructure

📌 Project Status
✔ DEPLOYED SUCCESSFULLY
✔ PRODUCTION READY BASE ARCHITECTURE
✔ FULL CLOUD STORAGE SYSTEM OPERATIONA
