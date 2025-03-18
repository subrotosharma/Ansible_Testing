#Ansible Topics
0. Enable call backs in ansible.cfg 
   [defaults]
   callbacks_enabled = timer, profile_tasks, profile_roles
   #The above provided playbook and task execution time which can allow us to identiy slow running playbooks.
   Enable Ansible Log in export ANSIBLE_LOG_PATH=~/ansible.log
   export ANSIBLE_DEBUG=True

1. Adhoc commands *
   ansible -i invfile pvt -m ping
   ansible -i invfile pvt -m shell -a "df -h"
   ansible -i invfile pvt -m shell -a "df -h | grep -i /dev/root" -vvvv
   ansible -i invfile server01:server02 -m shell -a "df -h | grep -i /dev/root"
   ansible -i invfile 'all:!server01' -m shell -a "df -h | grep -i /dev/root"
   ansible -i invfile 'all:&megastar' -m shell -a "df -h | grep -i /dev/root"
   ansible -i invfile2 'all:&megastar' -m shell -a "df -h | grep -i /dev/root"
   ansible -i invfile pvt -m user -a "name=superstar state=present" --become
   ansible -i invfile pvt -m shell -a "cat /etc/passwd | grep -i superstar"
   ansible -i invfile pvt -m setup #Prints ansible_facts for clients
   
2. with_items for running iterations. *
3. when condition *
4. Register output & return code using rc *
5. Ansible facts using Redis & Notify & Handlers & get_url & unarchive modules in redis   playbook.
* * * * * ansible -i /root/ansiblecode/invfile all -m setup
If you are unable to connect to clients, then redis is also be a issue. Disable redis config and try again.

6. Copy, File, No_Log, Debug *
7. Verbosity using -vvvv
9. ignore_errors: true *
10. block, rescue & always
11. Vault Encrypt String and File for aws_creds *
12. shell & command modules *
13. become_user *
15. serial option select how many machine can run at a time. serial 1 will run  
    on   one machine only. *
16. lineinfile *
17. Docker Swarm Configuration *
18. Set-fact *
19. --extra-vars ansible_user='ubuntu' 
20. fetch
21. tags *
22. Jinja Templates *
23. Pre & Post Tasks *
24. Roles and Ansible Galaxy *
25. Dynamic Inventory
26. AWX

