# :cherries: RPi tooling :cherries: 
Collection of roles for deploying different useful services to the Raspberry Pi

# Roles
 - **rpi_install_docker** - Install docker on the Pi
 - **rpi_install_bind** - Install Bind9 DNS server on the Pi using docker containers
 - **rpi_install_wireguard** - Install Wireguard VPN server on the Pi

# IMPORTANT
Before executing the Ansible pipeline, please install the python requisites:
~~~
pip3 install -r requirements.txt
~~~

# Roadmap
- [ ] Migrate Rpi bootstrap to this repo
- [x] Role for installing docker 
- [x] Role for deploying Bind9 using docker containers
- [x] Role for deploying Wireguard vpn (**Needs hardening**)
- [x] Role for installing DuckDNS ddns
- [ ] Role for deploying Grafana and InfluxDB
- [ ] Role for getting certificates from Let's encrypt
- [ ] Role for deploying Jenkins/Gitlab CI/CD
- [ ] Role for installing Go
- ...More to come!

# Contributing
If you're feeling like automating everything, from deployment to monitoring in your Pi, please feel free to send pull request on regards whatever service you'd like to have :blush:   
Also if you find some bug or want a new feature, please feel free to send your PR!  

# License
BSD
