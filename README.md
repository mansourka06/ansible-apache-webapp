# ansible-apache-webapp

This repository is setup to automate the configuration and deployment of a Apache Web Application using Ansible.

## Os available
- [x] Debian
- [ ] RedHat
- [ ] Windows server 2012
- [ ] Windows server 2016

## Variables
- The default variables are [here ...](vars/main.yml)

## Getting Start
1. **Clone the repository**: 
   ```
   git clone https://github.com/mansourka06/ansible-apache-webapp.git
   cd ansible-apache-webapp
   ```
2. Adapt and update your apache configuration files to **templates** directory.

3. Adapt and Update variables in [vars/main.yml](ansible-apache-web_server/vars/main.yml) with your webapp vars.

4. Add your inventory hostname in **inventory.ini** file

5. Run the playbook with the follwing ansible adoc command:
   
- `playbook.yml -i your-inventory-file  your-playbook-name.yml`
- **Exemple:**  `ansible-playbook -i inventory.ini playbook.yml`

## Contributing
Contributions are welcome! If you find any issues or want to improve this project, please open an issue or submit a pull request.

## Author
[Mansour KA](https://github.com/mansourka06)
