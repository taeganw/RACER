# RACER - Resilient Ansible Cyber Education Range
Educational resource for cybersecurity research and software analysis is critical to understanding the nature of communication across a critical infrastructure network. A resilient cyber range for students to practice creating a dynamic defense-in-depth network leverages multiple systems and software to create a realistic learning environment. Providing total visibility through services for inventory management, state monitoring, event monitoring, and incident management need to exist outside of the scope of the environment to ensure the productivity of the lab and its exercises. With a primary goal to use open-source software throughout the environment, this research highlights the use of resilience of the lab through the creation of Ansible scripts. These Ansible scripts remove the human factor from the creation of services such as Nagios, Trac, Security Onion, Suricata, and RT-IR to provide total visibility and fast reproduction of the environment to safely analyze and practice blue team and red team concepts. The final scripts created can be found on Github at https://github.com/taeganw/RACER where they will continue to grow into living code.

## How to Run the Playbook
**Varaibles File** - Ansible has 3 main files and folders for operation. Variables that can be changed by the user before running the script are found in the all.yml file in the group\_vars folder.

**Main Playbook File** - The initial playbook file holds the main Ansible commands to query information about the client to be configured, tasks to be performed, or roles to be assigned to clients. It is found in the install directory and is named configure-environment.yml.

**Hosts File** - The last important file to consider is the host's file which groups hosts on the network and defines the user to execute commands via SSH.

Once the 3 files are configured to your environment, ensure you can ssh into each machine you would like to configure. If there are services that you do not need in the environment, simply leave the group in the hosts field blank.

From the root directory run the playbook with
> ansible-playbook -i hosts ./install/configure-environment.yml -K
**-i specfies the hosts file to use
-K prompts for a password to elevate privilleges on the remote machine (a more secure method would be to implement Ansible Vault) **
