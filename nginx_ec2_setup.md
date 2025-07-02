# 🚀 EC2 Deployment with Nginx

## ✅ Public IP Address
Example:  
`http://34.60.66.56`

---

## 🔧 Steps Followed

### 1. Launch EC2 Instance
- Go to **AWS Console → EC2 → Launch Instance**
- Select **AMI**: Ubuntu 22.04 (LTS)
- Choose **Instance Type**: `t2.micro` (Free tier eligible)
- Create a new **Key Pair (.pem)** and download it
- Configure **Security Group** to allow:
  - SSH (port 22)
  - HTTP (port 80)

---

### 2. Connect to EC2 via SSH

```bash
chmod 400 your-key.pem
ssh -i your-key.pem ubuntu@<your-ec2-public-ip>

---

**### 3. Install Nginx, Host Sample Page, and Test in Browser**
After connecting via SSH, run the following commands:

```bash
# Update package list and install Nginx
sudo apt update && sudo apt install nginx -y

# Create a simple HTML page
echo "🚀 Hello from EC2!" | sudo tee /var/www/html/index.html

**### 4. Open your browser and go to:**

http://<your-ec2-public-ip>
**✅ You should see the message:**
🚀 Hello from EC2!

**🎉 Success!**
Your EC2 instance is now hosting a live Nginx-powered webpage!

![2](https://github.com/user-attachments/assets/e70cb65f-6f75-4447-b4ca-b8657f3570ab)

![1](https://github.com/user-attachments/assets/3c0a069d-0280-4075-bd6e-4679f365617a)
