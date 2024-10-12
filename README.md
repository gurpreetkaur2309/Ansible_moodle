

# Ansible Playbook for Moodle Installation

This repository contains an Ansible playbook to automate the installation of Moodle on an Ubuntu server. The playbook handles everything from installing Apache, MySQL, and PHP to setting up the Moodle database and configuring the Moodle environment.

## Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Files Included](#files-included)
- [Usage](#usage)
- [Customization](#customization)
- [Support](#support)
- [License](#license)

## Introduction

Installing Moodle manually can be a time-consuming and error-prone process. This Ansible playbook automates the installation, allowing you to deploy Moodle on any Ubuntu server in under an hour. The playbook installs all prerequisites and configures Moodle with just a few commands.

## Prerequisites

Before running this Ansible playbook, make sure you have the following:

- **Ansible** installed on your local machine.
- An **SSH key** to access your target server.
- An **AWS account** if you're using EC2 instances (optional).
- Basic understanding of Ansible, including how to set up an inventory file.

## Files Included

1. **`moodle_playbook.yml`**: The main Ansible playbook that installs Moodle.
2. **`inventory`**: The inventory file containing the target host details.

## Usage

1. **Clone the Repository**:
   ```bash
   git clone Ansible_moodle
   cd Ansible_moodle
   ```

2. **Update the Variables**: In the `moodle_playbook.yml`, update the following variables to match your requirements:
   - `mysql_root_password`: Set your MySQL root password.
   - `moodle_db_name`: Name of the Moodle database.
   - `moodle_db_user`: Username for the Moodle database.
   - `moodle_db_password`: Password for the Moodle user.

3. **Configure the Inventory File**: Add the public IP addresses or domain names of your target servers in the `inventory` file. Example:
   ```
   [moodle]
   your_server_ip
   ```

4. **Run the Playbook**:
   ```bash
   ansible-playbook -i inventory moodle_playbook.yml
   ```

5. **Access Moodle**: Once the playbook completes, you can access your Moodle instance by navigating to the server's public IP address in your web browser:
   ```
   http://<server_ip>/moodle
   ```

## Customization

- **Change Moodle Version**: To install a different version of Moodle, update the `moodle_version` variable in the playbook.
- **Database Settings**: Modify the MySQL root and Moodle database credentials in the playbook as per your requirement.
  
## Support

If you run into any issues or have questions, feel free to open an issue in this repository or reach out via email.

## License

This project is licensed under the MIT License.

---
