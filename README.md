# AWS-3-Tier-Architecture-Provisioned-and-Configured-with-Ansible

This project demonstrates the deployment of a **3-Tier Architecture** on **AWS EC2 instances** using **Ansible automation**.
The setup includes a **Proxy Server**, an **Application Server**, and a **Database Server**, all configured automatically using a single Ansible playbook.

---

## 📌 Architecture Overview

The architecture follows a classic 3-tier design:

```
Client Browser
     |
     |  (Port 326)
     v
Proxy Server (Nginx Reverse Proxy)
     |
     |  (Port 80)
     v
Application Server (Nginx + PHP-FPM)
     |
     v
Database Server (MariaDB)
```

---

## 🛠️ Technology Stack

* **Cloud Platform:** AWS EC2 (Amazon Linux)
* **Automation Tool:** Ansible
* **Web Server:** Nginx
* **Application Runtime:** PHP + PHP-FPM
* **Database:** MariaDB
* **Architecture Type:** 3-Tier (Proxy → App → DB)

---

## 📂 Project Structure

```
3-tier-ansible-project/
├── 3-tier.yml
├── inventory.ini
├── README.md
└── img/
    ├── ansible_playbook_run.png
    ├── proxy_server_status_active.png
    ├── app_nginx_php_status.png
    ├── db_database_created.png
    ├── final_output_browser.png
    └── servers.png
```

---

## ⚙️ Inventory Configuration

The `inventory.ini` file defines the target servers:

```ini
[proxy_server]
172.31.47.179 ansible_user=ec2-user ansible_ssh_private_key_file=/home/ec2-user/com.pem

[app_server]
172.31.32.73 ansible_user=ec2-user ansible_ssh_private_key_file=/home/ec2-user/com.pem

[db_server]
172.31.41.13 ansible_user=ec2-user ansible_ssh_private_key_file=/home/ec2-user/com.pem
```

---

## Deployment Steps

### 1️⃣ Clone the Repository

```bash
git clone [https://github.com/<your-username>/<your-repo-name>.git](https://github.com/RajAhire-1/AWS-3-Tier-Architecture-Provisioned-and-Configured-with-Ansible.git)
cd <your-repo-name>
```

### 2️⃣ Update Inventory File

Update `inventory.ini` with your EC2 private IPs and SSH key path.

### 3️⃣ Run Ansible Playbook

```bash
ansible-playbook -i inventory.ini 3-tier.yml
```

### 4️⃣ Verify Services

* **Proxy Server:** Nginx running and listening on port `326`
* **App Server:** Nginx + PHP-FPM running
* **DB Server:** MariaDB running with database created

### 5️⃣ Access the Application

Open your browser and navigate to:

```
http://172.53.64.46:326
```

---

## Screenshots

### Ansible Playbook Execution

![Ansible Playbook Run](img/ansible_playbook_run.png)

### Proxy Server Nginx Status

![Proxy Server Nginx Status](img/proxy_server_status_active.png)

### Application Server Nginx and PHP-FPM Status

![Application Server Status](img/app_nginx_php_status.png)

### Database Server – Database Created

![Database Server Database](img/db_database_created.png)

### Final Application Output in Browser

![Final Browser Output](img/final_output_browser.png)

### AWS EC2 Instances Overview

![AWS EC2 Instances](img/servers.png)

---

## ✅ Validation Summary

* Reverse proxy working on custom port **326**
* Requests forwarded from Proxy → App Server
* PHP application executed successfully
* MariaDB installed and database created
* Fully automated using Ansible

---

## 🎯 Key Highlights

* Simple and clean Ansible playbook
* No manual server configuration
* Real-world DevOps use case
* Resume and interview ready project

---

## 🧠 Interview Ready Explanation

> "This project demonstrates a 3-tier architecture where Nginx acts as a reverse proxy, forwarding traffic to an application server running PHP, with MariaDB as the backend database. The entire setup is automated using Ansible."

---

## 📌 Conclusion

This project showcases practical **DevOps automation skills**, infrastructure understanding, and hands-on experience with **Ansible and AWS**. It reflects a real-world production-style deployment in a simple and effective manner.

---

If you like this project, don’t forget to star the repository!
