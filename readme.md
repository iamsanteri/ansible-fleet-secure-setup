Ansible setup template for the initial login and setup on a desired amount of nodes.

1. After provisioning clean VMs, update your hosts file with current IPs of your fleet -> Then run the setup playbook:

`ansible-playbook -i hosts setup.yml`

2. Ansible will prompt for info and log into all VMs as root from your local machine and create non-root 'ansible' users on each of the new VMs

3. Ansible then sets up the non-root 'ansible' user to be required for secure connections from now onwards

4. Finally, Ansible de-commissions root access and locks the root logins for host machines (more secure)

5. You are good to go, use the 'ansible' user to securely log into the VMs you provisioned. You can now manage your fleet with Ansible from your local machine.

Example login: 

`ssh ansible@xx.xxx.xx.x`

Warning! This playbook is not extensively tested on every machine or situation, so errors are likely. In case of obscure erros, use this file as a guideline to implement more extensive rapid setup functionality to set up and configure your own set of secured fleet of remote machines.
