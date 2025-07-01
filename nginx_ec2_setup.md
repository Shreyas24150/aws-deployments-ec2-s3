# 🚀 EC2 Deployment with Nginx

## ✅ Public IP Address:
`http://<your-ec2-public-ip>`  
Example: `http://13.60.74.47`

---

## 🔧 Steps Followed:

### 1. Launch EC2 Instance
- Go to AWS Console → EC2 → Launch Instance
- AMI: Ubuntu 22.04
- Instance Type: `t2.micro` (Free tier eligible)
- Create new key pair (`.pem`) and download it
- Allow **SSH (22)** and **HTTP (80)** in Security Group

---

### 2. Connect via SSH
```bash
chmod 400 your-key.pem
ssh -i your-key.pem ubuntu@<your-ec2-public-ip>

---

### 3. Install nginx
after doing ssh install nginx
``bash
sudo apt update && sudo apt install nginx -y

---

### 4. Create a Sample Web Page
``bash
echo "🚀 Hello from EC2!" | sudo tee /var/www/html/index.html

### 5. View in Browser
Go to:
http://<your-ec2-public-ip>
You should see your custom message.
