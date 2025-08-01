# Jenkins-work
## ✅ Prerequisites

- AWS account with EC2 access
- Ubuntu EC2 instance (Ubuntu 20.04/22.04 preferred)
- Security Group with the following inbound rules:
  - **SSH (22)** – for terminal access
  - **HTTP (80)** – optional for web access
  - **Custom TCP (8080)** – Jenkins web UI

---

## 🔧 Step-by-Step Installation

### 1. Connect to EC2

```bash
ssh -i your-key.pem ubuntu@<your-ec2-public-ip>
2. Update System
bash
Copy code
sudo apt update && sudo apt upgrade -y
3. Install Java
bash
Copy code
sudo apt install openjdk-17-jdk -y
java -version
4. Add Jenkins Repository and Key
bash
Copy code
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
5. Install Jenkins
bash
Copy code
sudo apt update
sudo apt install jenkins -y
6. Start and Enable Jenkins
bash
Copy code
sudo systemctl start jenkins
sudo systemctl enable jenkins
🌐 Access Jenkins Web UI
Open your browser and go to:

text
Copy code
http://<your-ec2-public-ip>:8080
Example: http://18.208.145.185:8080

🔐 Unlock Jenkins
Retrieve the admin password:

bash
Copy code
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
Copy the password and paste it into the Jenkins setup screen in your browser.

📦 Install Plugins
Select:

text
Copy code
Install Suggested Plugins
Wait for the plugin installation to complete.

👤 Create Admin User
Fill in the form with your preferred credentials:

text
Copy code
Username: pratiksha
Password: yourpassword
Full name: Pratiksha Bhosale
Email: your@email.com
