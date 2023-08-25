# Ansible_Zabbix_Installer
This is an Ansible Scrypt to install Zabbix 6.0 for Ubuntu 22.04 with its dependencies
!! This Version is not Idempotent !!

Dependencies to install beforhand:
  - sudo apt install python3-pip git
  - pip3 install ansible-core
  - nano ~/.bashrc
add "export PATH=$PATH:/home/'whoami'/.local/bin", close (ctrl + x) & save
  - source ~/.bashrc
  - ansible-galaxy collection install community.crypto community.general community.mysql
  - then clone this repo and move to the playbooks folder
To run the playbook:
ansible-playbook script.yml -e auth_os_user='whoami' -e 'ansible_python_interpreter: /usr/bin/python3' -K

!! Inside the Playbook there is a Variable called  "- password_db: ", wich is the password for the Zabbix database user !!
The default Zabbix Superuser is {Username: Admin, Password: zabbix}
