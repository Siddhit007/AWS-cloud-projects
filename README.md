# -AWS-Beginner-Projects-Siddhi
This repository contains my hands-on beginner projects on AWS, focusing on core services like EC2, web servers, and S3.
AWS Beginner Projects – Siddhi

This repository contains my hands-on beginner projects on AWS, focusing on core services like EC2, web servers, and S3.

📌 Project 1: Hosting a Website on EC2 (Nginx)
🔹 Objective

Launch an EC2 instance and host a static website using Nginx.

🔹 Steps
Launch EC2 instance (Amazon Linux 2, t2.micro)
Configure Security Group:
Allow SSH (Port 22)
Allow HTTP (Port 80)

Connect to instance via SSH:

ssh -i <key.pem> ec2-user@<public-ip>

Install Nginx:

sudo yum update -y
sudo amazon-linux-extras install nginx1 -y
sudo systemctl start nginx
sudo systemctl enable nginx

Create custom webpage:

sudo nano /usr/share/nginx/html/index.html

Restart Nginx:

sudo systemctl restart nginx

Access website:

http://<public-ip>
🔹 Outcome

Successfully hosted a static website on EC2 using Nginx.

📌 Project 2: Adding Multiple Pages (Nginx)
🔹 Objective

Enhance website by adding multiple pages.

🔹 Steps

Navigate to web directory:

cd /usr/share/nginx/html

Create new page:

sudo nano about.html

Add link in index.html:

<a href="about.html">Go to About Page</a>

Restart Nginx:

sudo systemctl restart nginx
🔹 Outcome

Implemented multi-page website hosted on EC2.

📌 Project 3: Hosting Website using Apache
🔹 Objective

Replace Nginx with Apache web server.

🔹 Steps

Stop Nginx:

sudo systemctl stop nginx
sudo systemctl disable nginx

Install Apache:

sudo yum install httpd -y

Start Apache:

sudo systemctl start httpd
sudo systemctl enable httpd

Create webpage:

sudo nano /var/www/html/index.html

Restart Apache:

sudo systemctl restart httpd
🔹 Outcome

Successfully deployed website using Apache server.

📌 Project 4: S3 Static Website Hosting
🔹 Objective

Host a static website using Amazon S3.

🔹 Steps
Create S3 bucket (unique name)
Disable “Block all public access”
Upload website files (index.html, about.html)
Enable Static Website Hosting:
Index document: index.html
Add bucket policy for public access
Access via S3 endpoint URL
🔹 Sample Bucket Policy
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
🔹 Outcome

Hosted a static website using S3 without EC2.

🧠 Key Learnings
EC2 instance setup and SSH access
Security Groups and port configuration
Nginx vs Apache web servers
Static website hosting on S3
Basics of IAM policies and permissions
📌 Future Improvements
Use IAM roles for secure access
Integrate EC2 with S3
Set up Load Balancer
Use CloudFront for CDN
✨ Author

Siddhi Tilekar
