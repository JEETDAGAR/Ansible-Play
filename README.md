# Ansible Playbook for Web Server Setup

## Overview
This project uses Ansible to automate the installation and configuration of web servers. It includes a control node and two target servers, where one server hosts Nginx and the other hosts Apache (httpd). The project also contains playbooks for installation and uninstallation of the web servers.

## Architecture
- **Control Node**: This server runs Ansible and manages the configuration of other servers.
- **Target Servers**: 
  - **Server 1**: Hosts Nginx
  - **Server 2**: Hosts Apache (httpd)

## Project Structure
- **Inventory File**: Contains the list of servers and their configuration.
- **Playbooks**: 
  - `web_play.yaml`: Playbook for installing web servers and configuring index pages.
  - `revert_play.yaml`: Playbook for uninstalling web servers and cleaning up configurations.

## Steps

### 1. Setting Up Inventory
- Added both servers to the Ansible inventory.
- Configured SSH access using a PEM file to ensure secure connectivity.

### 2. Testing Connectivity
- Verified the connection to both servers by using the `ansible ping` command, confirming successful SSH access.

### 3. Creating the Playbook (`web_play.yaml`)
- **Purpose**: Install Nginx on Server 1 and Apache on Server 2, along with hosting an `index.html` file on each server.
  
  #### Key Tasks:
  - **Install Nginx on Server 1**:
    - Used `amazon-linux-extras` to enable and install Nginx.
    - Created a custom `index.html` file for Nginx.

  - **Install Apache on Server 2**:
    - Used the `yum` module to install Apache.
    - Created a custom `index.html` file for Apache.

### 4. Running the Playbook
- Executed the playbook using the command:
  ```bash
  ansible-playbook web_play.yaml
- Verified that both web servers were successfully installed and configured by accessing the respective IP addresses.
### 5. Reverting Changes (revert_play.yaml)
- **Purpose**: Uninstall Nginx and Apache and remove any configurations made during installation.

  #### Key Tasks:
   - **Removed Nginx from Server 1**.
   - **Removed Apache from Server 2**.
- Deleted the index.html files from both servers.
### 6. Running the Revert Playbook
- Executed the revert playbook using the command:
  ```bash
  ansible-playbook revert-play.yaml
## **Conclusion**
This project effectively demonstrates the use of Ansible for automating the deployment and management of web servers. The playbooks can be reused and modified for different server configurations or additional applications.

## **Contributing**

If you find any issues or have suggestions for improvements, feel free to open an issue or submit a pull request. **Contributions are always welcome!**

## **Connect**

If you have any questions or want to discuss about DevOps, Kubernetes, Cloud or anything else, feel free to reach out!

**LinkedIn**: https://www.linkedin.com/in/jeet-dagar-0463621b7/
