## 🚀 Deploy Thrive Africa Static Site on EC2 (Amazon Linux + NGINX)

### Prerequisites:
- Amazon Linux 2 EC2 instance
- Port 80 open in the security group
- Public GitHub repo with your website (e.g., index.html)

### Deployment Commands:

```bash
# Update system and install Git
sudo yum update -y
sudo yum install -y git

# Enable and install NGINX

sudo yum install -y nginx

# Start and enable NGINX to run on boot
sudo systemctl start nginx
sudo systemctl enable nginx

# Clean default web directory
sudo rm -rf /usr/share/nginx/html/*

# Clone your GitHub repo into NGINX web root
git clone https://github.com/your-username/thrive-africa.git

# Step 2: Move the website files into the NGINX web root
sudo mv thrive-africa/* /usr/share/nginx/html/

# (Optional) Set proper permissions
sudo chown -R nginx:nginx /usr/share/nginx/html

# Open in browser
# http://<your-ec2-public-ip>
