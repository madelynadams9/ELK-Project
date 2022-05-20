## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.
![Azure VM Topology](https://user-images.githubusercontent.com/61891953/169565344-9e34df08-6bcc-4ed1-abda-8ade9e5035f4.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build

### Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.

A jumpbox or bastion server serves as a gatway to gain entry into a remote network. Many times the primary mode of access is ssh and without the key access is forbidden
A loadbalancer is meant to serve as a specific point of access for a service that is served by multiple machines. This allows high availability models to function properly
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log files and system resources.

Filebeat is meant primarily to watch for system logs and forward any changes to the Elasticsearch Host
Metricbeat is used only for gathering metrics and system resources usage for display in Elasticsearch
The configuration details of each machine may be found below.

![image](https://user-images.githubusercontent.com/61891953/169572136-d192172c-1bc6-4bc4-a077-a1aa3ab67029.png)

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from my public IP

Machines within the network can only be accessed by JumpBox host.
JumpBox: Public IP is 20.213.91.203
         Private IP is 10.0.0.4

A summary of the access policies in place can be found in the table below.
![image](https://user-images.githubusercontent.com/61891953/169598291-6dfce950-0e2f-4289-b402-52f8b965c5cb.png)

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
-It allows for full automation of a specific server and reduces configuration errors

The playbook implements the following tasks:
- Install Docker: Installs the core docker code to the remote server
- Install Python3_pip: Pip is an installation module that allows for additional docker modules to be installed easier
- Docker Module: Tells the previous PIP module to install the necessary docker component modules
- Increase Memory/Use More Memory: A common issue with the ELK Docker image is to little memory. This help fix the issue to allow the server to launch
- Download and Launch ELK Container: This downloads the ELK docker container and initializes it with the specified ports being published

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5
- 10.0.0.6
- 10.1.0.4

We have installed the following Beats on these machines:
- Web 1, Web 2

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?
