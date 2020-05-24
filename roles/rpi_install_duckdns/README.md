rpi_install_duckdns
=========

A simple Ansible role to install duckdns script for dynamic DNS using cron service.  
It creates a system user called **duckdns** and executes the script recurrently from that user.

Requirements
------------

No especial requirements are needed, apart from remote hosts to hace curl and cron. 

Role Variables
--------------

**duckdns_token**: Token provided when registering to duckdns service. (i.e. *4d75154b-ba9e-4afb-83a5-d94c806c7399*)  

**duckdns_script_exec_time_minutes**: Minutes for the script to execute recurrently from cron (i.e. *5*)  

Dependencies
------------

This role doesn't have any external role dependencies.  

Example Playbook
----------------
~~~
- name: Install duckdns for DDNS name resolution
  hosts: rpi
  become: yes
  roles:
    - rpi_install_duckdns
  tags:
    - duckdns
~~~

License
-------

BSD

Author Information
------------------

Miguel Sama (miguelsamamerino@gmail.com)
