### Ansible playbook for the initial secure setup of a fleet with a desired amount of nodes

1. After provisioning fresh VMs, update your hosts file with current IPs of your fleet

`nano hosts`

2. Next, run the setup playbook:

`ansible-playbook -i hosts setup.yml`

2. Ansible will prompt you for info and thereafter log into all VMs as root from your local machine creating non-root 'ansible' users on each of your specified VMs

From this point onwards, the non-root 'ansible' user must be used for secure connections into each VM individually, or centrally from your control node

4. Ansible de-commissions root access and locks the root logins for host machines making your fleet more secure

5. You are good to go, use the 'ansible' user to securely log into VMs you provisioned. You can now manage your fleet centrally with Ansible from your local machine

Example login for your freshly configured VM: 

`ssh ansible@xx.xxx.xx.x`

Warning! This playbook is not extensively tested on every machine or situation, so errors are likely. In case you hit obscure erros, use this file as a guideline to implement more extensive setup functionality to configure your fleet of remote machines.
