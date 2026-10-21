
# ShopEasy - E-commerce Deployment Using Ansible

## Project Overview

ShopEasy is a sample e-commerce website deployed automatically using Ansible and Nginx. This project demonstrates configuration management and web server deployment on Ubuntu running through Windows Subsystem for Linux (WSL).

## Objectives

- Automate web server installation using Ansible.
- Deploy a static e-commerce website using an Ansible playbook.
- Manage configuration using an inventory file.
- Verify the deployment through HTTP and service-status checks.
- Maintain project files and documentation using Git and GitHub.

## Technologies Used

- **Operating System:** Ubuntu on WSL
- **Configuration Management:** Ansible
- **Web Server:** Nginx
- **Frontend:** HTML and CSS
- **Version Control:** Git
- **Repository Hosting:** GitHub

## Project Structure

```text
ecommerce-devops/
├── inventory.ini
├── playbook.yml
├── index.html
├── README.md
└── screenshots/
```

## Project Files

- **`inventory.ini`** — Defines the local target host and Ansible connection.
- **`playbook.yml`** — Automates package updates, Nginx installation, webpage deployment, and service management.
- **`index.html`** — Contains the ShopEasy e-commerce webpage.
- **`screenshots/`** — Stores screenshots documenting implementation and testing.

## How It Works

1. Ansible reads the inventory file to identify the target host.
2. The playbook updates the package cache.
3. Ansible installs Nginx on Ubuntu.
4. The HTML webpage is copied to `/var/www/html/index.html`.
5. Ansible ensures that the Nginx service is running.
6. The deployed website is tested using HTTP requests and browser access.

## Setup and Execution

### 1. Install the required tools

Install Ubuntu, Ansible, Git, and Nginx as appropriate for your environment. Nginx is installed automatically by the playbook.

### 2. Navigate to the project directory

```bash
cd ecommerce-devops
```

### 3. Validate the inventory

```bash
ansible-inventory -i inventory.ini --list
```

### 4. Check playbook syntax

```bash
ansible-playbook -i inventory.ini playbook.yml --syntax-check
```

### 5. Run the playbook

```bash
ansible-playbook -i inventory.ini playbook.yml --ask-become-pass
```

Enter your Ubuntu password when prompted.

### 6. Verify the deployment

Check the Nginx service:

```bash
systemctl is-active nginx
```

Check the HTTP response:

```bash
curl -I http://localhost
```

Open the website in your browser:

http://localhost

## Test Results

The deployment was successfully verified in the local Ubuntu environment.

| Test | Expected Result | Observed Result |
|---|---|---|
| Inventory validation | Host recognized | Passed |
| Playbook syntax check | No syntax errors | Passed |
| Ansible deployment | No failed or unreachable hosts | Passed |
| Nginx service check | `active` | `active` |
| HTTP response | `200 OK` | `200 OK` |
| Webpage title | ShopEasy - Online Shopping | Verified |

## Conclusion

This project demonstrates how Ansible automates web server configuration and website deployment. The successful deployment and verification of ShopEasy show how configuration management can reduce repetitive manual tasks and make deployment more consistent.

## Future Scope

- Deploy a dynamic e-commerce application.
- Integrate automated testing into a CI/CD pipeline.
- Configure HTTPS using TLS certificates.
- Deploy the application to a cloud server.
- Extend Ansible automation to multiple web servers.

## Author

**Name:** Soha Sameer Sayyed  
**GitHub:** [SohaSayyed](https://github.com/SohaSayyed)

**Project:** E-commerce Web Application Deployment and Configuration Management Using Ansible
