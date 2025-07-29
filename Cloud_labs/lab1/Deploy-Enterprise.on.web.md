**LAB : Deploying an Enterprise Web**

Deploying an Enterprise Web Lab on Huawei Cloud involves creating a simulated enterprise environment to develop, deploy, and test a full web application using Huawei’s cloud services. This setup can be used for learning, testing, development, or demonstration purposes.

**Steps to Deploy an Enterprise Web Application**

**🧠 What is Deployment?**

Deployment means making a web application available for users on a server, cloud platform, or internet. In a lab setup, you simulate real-world enterprise deployment for learning or testing.

**1:****Initial Setup and Account Login******

Before starting, log in to Huawei Cloud using the provided IAM lab account via Google Chrome. This ensures access to the necessary cloud environment without using personal credentials.

**🏗️ Enterprise Web Lab Setup – Key Components**

**Component **  	                           ** Description  **          	                     ** Example Tools**

  Frontend                	                  What users see	                                 HTML, CSS, JS, React

  Backend                            	       Handles logic & data	                        Node.js, Django, Java Spring Boot

  Database                            	     Stores information	                            MySQL, PostgreSQL, MongoDB


Version Control	                              Tracks changes	                                     Git, GitHub

Server / Hosting	                          Where the app runs	                           Huawei ECS, Local VM, AWS EC2

  Web Server                                  Serves content	                                       NGINX, Apache

   CI/CD	                                    Auto deployment	                                GitHub Actions, Jenkins
   

   🧪 Lab Deployment – Step-by-Step Explanation
   
   **🔹 Step 1: Develop the Web Application**
   
Code frontend and backend locally.

Example: Create a login page (frontend) and a login API (backend).

**🔹 Step 2: Push Code to GitHub**

Use Git to upload your project.

git init

git add .

git commit -m "Initial Commit"

git remote add origin https://github.com/your-repo.git

git push -u origin main

**🔹 Step 3: Prepare Deployment Server**

Use Huawei ECS, Virtual Machine, or Docker.

Update and install necessary software:

bash

sudo apt update

sudo apt install nginx nodejs npm





