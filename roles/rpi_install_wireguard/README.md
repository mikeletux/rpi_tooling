rpi_install_wireguard
=========

This role is intended to install Wireguard on a Raspberry Pi to allow devices from outside the home network to connect to it. (Like being connected at home but actually not.)
The role HAS NOT BEEN THOUGHT to connect different networks among them.

Requirements
------------

This role doesn't have any prerequisites.

Role Variables
--------------


**wg_server_interface_addr**: IP address to be used in the wg0 interface (i.e. *10.0.0.1/24*).

**wg_server_listening_port**: UDP port where Wireguard daemon will be listening. Also this port will be opened in **ufw** (i.e. *"51820"*).

**wg_server_allowed_addr**: Dictionary of allowed IPs for peers as well as their public keys. (Using a /32 in the example, means the peer would need to configure that IP address, otherwise the server won't allow it to connect).
In example:  
~~~
wg_server_allowed_addr:
  - addr: 10.0.0.10/32
    public_key: xObbcWZ8WBqk4hrJInEdaCd2Bl4C+cY++JlS3NosrSU=
  - addr: 10.0.0.20/32
    public_key: XZAQaRNwT/VH+37B/DdbpFOksjQaTE5XIqbaX+CADlM=
~~~

**wg_replace_old_keys**: Flag that indicates to replace the private and public key, even thought they exist on config files. (i.e. *false* won't overwrite anything whilst *true* will update the keys on the config file).


Dependencies
------------

This role has no external dependencies.

Example Playbook
----------------

~~~
- name: Install WireGuard on RPi
  hosts: rpi
  become: yes
  roles:
    - rpi_install_wireguard
  tags:
    - wireguard
~~~

License
-------

BSD

Author Information
------------------

Miguel Sama (miguelsamamerino@gmail.com)
