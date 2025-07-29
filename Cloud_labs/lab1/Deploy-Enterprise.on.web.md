**LAB : Deploying an Enterprise Web**

Deploying an Enterprise Web Lab on Huawei Cloud involves creating a simulated enterprise environment to develop, deploy, and test a full web application using Huawei’s cloud services. This setup can be used for learning, testing, development, or demonstration purposes.

**🧠 What is Deployment?**

Deployment means making a web application available for users on a server, cloud platform, or internet. In a lab setup, you simulate real-world enterprise deployment for learning or testing.

🏗️ Architecture Overview

User ───> Huawei Cloud ECS ───> Backend App (Node.js / Java / Django)
                        │
                        └─> OBS (Static Files / Images)
                        └─> RDS (MySQL / PostgreSQL)

✅ Services Used

**Huawei Cloud Service	**                                     ** Purpose**

ECS (Elastic Cloud Server)	                    Host your backend/frontend app

OBS (Object Storage)	                           Store files (e.g., images)

RDS (Relational DB Service)                     	Manage databases securely

ELB (Optional)	                                 Load balancing for scaling

VPC	                                             Secure internal networking

**🧪 Step-by-Step Deployment Process**

**🔹 1. Create an ECS Instance**

**1**.Log in to Huawei Cloud.

**2**.Go to Elastic Cloud Server (ECS).

**3**.Click Create ECS.

OS: Ubuntu Server 22.04

Flavor: General-purpose (2vCPUs, 4GB RAM)

Add to a **new VPC and security group**

Set inbound rules: allow SSH (port 22), HTTP (80), HTTPS (443)

**🔹 2. Connect to ECS**

Use SSH from your terminal:

bash  

ssh your-user@your-ecs-public-ip

**🔹 3. Set Up the Web Environment**

Install necessary software:

For Node.js App:

bash

sudo apt update

sudo apt install nodejs npm nginx -y

**For Python/Django:**

bash

sudo apt install python3-pip python3-venv nginx -y


**🔹 4. Deploy Your Application**
bash

git clone https://github.com/your-org/your-enterprise-app.git

cd your-enterprise-app

Install and start your app:

bash

npm install

npm run build

npm start  # or use pm2

**🔹 5. Configure NGINX (Optional)**

Serve your frontend app or reverse proxy backend.

Edit config:

bash

sudo nano /etc/nginx/sites-available/default

**Example:**

bash

server {
    listen 80;
    
    server_name your-ecs-ip;

    location / {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}
**Restart:**

bash

sudo systemctl restart nginx

**🔹 6. Use OBS for Static Files**

Go to Object Storage Service (OBS) in Huawei Cloud.

Create a bucket (e.g., your-web-bucket).

Upload images, videos, or documents.

Generate public URLs to access files in your app.

**🔹 7. Use RDS for Database**

Go to Relational Database Service (RDS).

Create a MySQL or PostgreSQL instance.

Connect it from your app using credentials and host.

**📡 Access the Application**

http://your-ecs-public-ip


**✅ Benefits of Huawei Cloud for Enterprise Deployment**

Scalability: Add more ECS or auto-scaling.

Security: Secure groups and VPCs.

Reliability: RDS backups and monitoring.

Integration: Easy OBS + ECS + RDS integration

















