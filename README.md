# ansible-apache-webapp

This repository is setup to automate the configuration and deployment of an Apache Web Application using Ansible and Vagrant for testing.

## Introduction

Automating the setup of Apache web applications is essential for ensuring consistency, reliability, and efficiency in deployment processes. This repository provides a robust solution using Ansible, a powerful configuration management tool, along with Vagrant for easy testing in a virtual environment.

## Features

- Automates the installation and configuration of Apache web server.
- Deploys a sample web application to demonstrate the setup.
- Includes Vagrant configuration for testing the Ansible playbook and roles in a virtual environment.
  
## Os available

- [x] Debian
- [x] RedHat

## Prerequisites

Before you begin, ensure you have the following prerequisites:

- Ansible installed on your local machine.
- Basic understanding of Ansible playbooks and roles.
- Vagrant installed on your local machine.
- VirtualBox or another supported provider configured for Vagrant.

## Getting Started

To get started with deploying the Apache web application, follow these steps:

1. Clone this repository to your local machine:
```
git clone https://github.com/mansourka06/ansible-apache-webapp.git
```
2. Navigate to the cloned repository directory:

```
cd ansible-apache-webapp
``` 
   
3. Edit and update your apache configuration files to **templates** directory.

4. Review and customize the [vars file](../roles/apache-webapp/vars/main.yml) in the `vars` directory to configure the web application settings according to your requirements.

5. Edit the `inventory` file to specify the target hosts where you want to deploy the web application.

6. Run the Ansible playbook to deploy the Apache web application, with the followind ansible adoc command:
   
- `playbook.yml -i your-inventory-file  your-playbook-name.yml`
- Exemple:  `ansible-playbook -i inventory.ini playbook.yml`

7. Once the playbook execution is complete, access the deployed web application in your browser using the specified URL.

## Testing

### Using Vagrant

To test the Ansible playbook and roles using Vagrant, follow these steps:

1. Ensure Vagrant is installed on your local machine.

2. Navigate to the `vagrant` directory:

    ```
    cd vagrant
    ```

3. Use Vagrant to spin up the testing environment:

    ```
    vagrant up
    ```

4. Once the VM is provisioned, SSH into the VM:

    ```
    vagrant ssh
    ```

5. You can now run the Ansible playbook inside the VM to deploy the Apache web application:

    ```bash
    ansible-playbook -i inventory playbook.yml
    ```

6. Access the deployed web application in your browser using the specified URL.

## Cleanup

To tear down the Vagrant testing environment, run the following command:

```
vagrant destroy
```

### Using Github Action CICD

**Setting up github and github actions**
- Let’s add a Github Actions workflow in our project directory. Create a directory named .github and inside that directory create another directory named workflows. All our workflow files will be stored inside this directory. Create a file named [cicd.yml](.github/workflows/cicd.yml) which will make the complete path as`.github/workflows/cicd.yml`, inside we add the [code pipeline](.github/workflows/cicd.yml). This GitHub action allows you to run Ansible Playbook.

- Now, whenever I push to deploy branch, a new build will be triggered which will build and push the image to docker hub. The workflow is pretty simple and you may also extend it with running tests or performing other actions as per your requirements.

- Our workflow is now ready. Let’s test it by pushing something to the deploy branch. If you are using some other branch, push to the associated branch accordingly.

## Contributing
Contributions are welcome! If you find any issues or want to improve this project, please open an issue or submit a pull request.

## Author
[Mansour KA](https://github.com/mansourka06)
