# 🚀 AWS Beginner Projects – Siddhi

This repository contains my hands-on beginner projects on AWS, focusing on core services like EC2, web servers, and S3.

---

## 📌 Project 1: Hosting a Website on EC2 (Nginx)

### 🔹 Objective

Launch an EC2 instance and host a static website using Nginx.

### 🔹 Steps

1. Launch EC2 instance

   * AMI: Amazon Linux 2
   * Instance Type: t2.micro

2. Configure Security Group:

   * Allow SSH (Port 22)
   * Allow HTTP (Port 80)

3. Connect to instance via SSH:

   ```bash
   ssh -i <key.pem> ec2-user@<public-ip>
   ```

4. Install Nginx:

   ```bash
   sudo yum update -y
   sudo amazon-linux-extras install nginx1 -y
   sudo systemctl start nginx
   sudo systemctl enable nginx
   ```

5. Create custom webpage:

   ```bash
   sudo nano /usr/share/nginx/html/index.html
   ```

6. Restart Nginx:

   ```bash
   sudo systemctl restart nginx
   ```

7. Access website:

   ```
   http://<public-ip>
   ```

### 🔹 Outcome

Successfully hosted a static website on EC2 using Nginx.

---

## 📌 Project 2: Multi-Page Website (Nginx)

### 🔹 Objective

Enhance the website by adding multiple pages.

### 🔹 Steps

1. Navigate to web directory:

   ```bash
   cd /usr/share/nginx/html
   ```

2. Create new page:

   ```bash
   sudo nano about.html
   ```

3. Update index.html:

   ```html
   <a href="about.html">Go to About Page</a>
   ```

4. Restart Nginx:

   ```bash
   sudo systemctl restart nginx
   ```

### 🔹 Outcome

Implemented a multi-page website hosted on EC2.

---

## 📌 Project 3: Hosting Website using Apache

### 🔹 Objective

Replace Nginx with Apache web server.

### 🔹 Steps

1. Stop Nginx:

   ```bash
   sudo systemctl stop nginx
   sudo systemctl disable nginx
   ```

2. Install Apache:

   ```bash
   sudo yum install httpd -y
   ```

3. Start Apache:

   ```bash
   sudo systemctl start httpd
   sudo systemctl enable httpd
   ```

4. Create webpage:

   ```bash
   sudo nano /var/www/html/index.html
   ```

5. Restart Apache:

   ```bash
   sudo systemctl restart httpd
   ```

### 🔹 Outcome

Successfully deployed website using Apache server.

---

## 📌 Project 4: S3 Static Website Hosting

### 🔹 Objective

Host a static website using Amazon S3.

### 🔹 Steps

1. Create S3 bucket (unique name)
2. Disable “Block all public access”
3. Upload website files (index.html, about.html)
4. Enable Static Website Hosting:

   * Index document: index.html
5. Add bucket policy for public access
6. Access via S3 endpoint URL

### 🔹 Sample Bucket Policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicRead",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::<bucket-name>/*"
    }
  ]
}
```

### 🔹 Outcome

Hosted a static website using S3 without EC2.

---

## 🧠 Key Learnings

* EC2 instance setup and SSH access
* Security Groups and port configuration
* Nginx vs Apache web servers
* Static website hosting on S3
* Basics of IAM policies

---

## ✨ Author

Siddhi Tilekar
