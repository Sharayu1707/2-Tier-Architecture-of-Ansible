# 2-Tier-Architecture-of-Ansible

# Overview

This project demonstrates the deployment of a 2-tier application architecture using Ansible with a single playbook.

## Application Server:

Nginx Web Server

PHP & PHP-FPM

PHP application deployment

## Database Server:

MariaDB Server

Database creation

The setup is fully automated using Ansible to ensure consistency, scalability, and faster deployments.

# Technologies Used

Ansible

Nginx

PHP / PHP-FPM

MariaDB

Linux 

📁 Inventory Structure

    [appserver]
    172.31.15.216 ansible_user=ec2-user ansible_ssh_private_key_file=/home/ec2-user/jenkins.pem

    [dbserver]
    172.30.12.216 ansible_user=ec2-user ansible_ssh_privae_key_file=/home/ec2-user/jenkins.pem

# Ansible Playbook

Single playbook handles both tiers:

Application server setup

Database server setup

App Server Tasks

Install Nginx, PHP, PHP-FPM

Start & enable services

Deploy PHP test page (phpinfo())

DB Server Tasks

Install MariaDB

Start & enable MariaDB service

Create database

# How to Run the Playbook

Clone the repository

git clone https://github.com/your-username/2-tier-ansible.git

cd 2-tier-ansible


Update inventory

vi inventory.ini


Run Ansible playbook

ansible-playbook -i inventory.ini 2-tier.yml

✅ Verification
Application Server

Open in browser:

http://<APP_SERVER_IP>/index.php


You should see the PHP info page.

Database Server

Login to DB:

mysql -u root


Check database:

SHOW DATABASES;


Database FCT should be present.

# Benefits of This Approach

Automated deployment

Idempotent execution

Single playbook for multi-tier architecture

Beginner-friendly & interview-ready

# Use Case

DevOps practice

Interview projects

Infrastructure automation

Learning Ansible multi-host deployments

# Future Improvements

Use Ansible roles

Secure MariaDB with Ansible module

Connect PHP app to database

Add handlers & templates
