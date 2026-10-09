# Ansible Multi-Project Deployment

## Project Overview

This project demonstrates how to automate the deployment of multiple web projects using Ansible and Nginx.

A single Ansible playbook and reusable role deploy three separate web projects. Project-specific settings are maintained in Ansible variables, while Jinja2 templates generate the website pages and Nginx server configurations.

## Technologies Used

* Ansible
* Linux (Ubuntu)
* Nginx
* YAML
* Jinja2 Templates
* Git and GitHub

## Project Structure

```text
multi-project/
├── site.yml
└── roles/
    └── webapp/
        ├── handlers/
        │   └── main.yml
        ├── tasks/
        │   └── main.yml
        ├── templates/
        │   ├── index.html.j2
        │   └── project.conf.j2
        └── vars/
            └── main.yml
```

## Features

* Deploys multiple web projects using a single playbook.
* Uses Ansible roles for reusable and organized automation.
* Stores project names, ports, and messages in variables.
* Uses loops to deploy projects without duplicating tasks.
* Uses Jinja2 templates to generate HTML pages and Nginx configurations.
* Uses handlers to restart Nginx when relevant files change.
* Enables Nginx configurations using symbolic links.

## Projects Deployed

| Project   | Port | Welcome Message      |
| --------- | ---: | -------------------- |
| Project A | 8083 | Welcome to Project A |
| Project B | 8084 | Welcome to Project B |
| Project C | 8085 | Welcome to Project C |

## How to Run

### 1. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd multi-project
```

Replace the placeholder with your repository URL.

### 2. Run the playbook

```bash
ansible-playbook -K site.yml
```

Enter the required sudo password when prompted.

### 3. Verify the websites

```bash
curl http://localhost:8083
curl http://localhost:8084
curl http://localhost:8085
```

You can also open these URLs in a browser running on the Ubuntu VM.

## Learning Outcomes

* Creating and using Ansible roles.
* Managing configuration through variables.
* Using loops to automate repetitive tasks.
* Working with Jinja2 templates.
* Managing services and handlers.
* Automating Nginx configuration and website deployment.
* Version-controlling infrastructure automation with Git.

## Author

Akshaya Karayi

