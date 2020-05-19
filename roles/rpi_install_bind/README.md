rpi_install_bind
=========

This role installs Bind9 DNS service on a docker containers

Requirements
------------

This Ansible role uses the **ipaddr** ansible filter. To make the role usable, please install **netaddr** package using pip.
~~~
pip3 install netaddr
~~~

Role Variables
--------------

**bind_docker_volume_folder**: Where you want to have you docker volume for Bind9 (*i.e. /srv/docker/bind*)  

**dns_domain**: DNS domain zone (*i.e. home.lan*)  

**pi_name**: Domain name wanted for you pi (*i.e. pi*) 
**dns_entries**: Dictionary with the A domains to add to the DNS server  
In example:
~~~
dns_entries:
  - name: gw
    ip: 192.168.1.1
  - name: 3d
    ip: 192.168.1.250
~~~

**dns_forwarder_server_1**: First public DNS server (use for find as forwarder 1. Also it is used a backup DNS server when the pi is being used. *i.e. 8.8.8.8*)  
**dns_forwarder_server_2**: Second public DNS server (use for find as forwarder . i.e. *8.8.4.4*)  

**bind_max_cache_size**: Max cache size for Bind9 (*i.e. 10m*)  

**netplan_file_name**: Netplan file used for configuring networking on the pi un the the folder /etc/netplan (*i.e. 50-ansible-managed-nw.yaml*)  

Dependencies
------------

This role has no dependencies on any other Ansible role

Example Playbook
----------------

~~~
- name: Install Bind9 on Pi
  hosts: rpi
  roles:
    - rpi_install_bind
~~~

License
-------

BSD

Author Information
------------------

Miguel Sama (miguelsamamerino@gmail.com)
