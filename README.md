# Cara menggunakan ansiblenya

## Basic


- Edit File ansible.cfg dan gunakan user ubuntu
- ping semua mesin
- ansible-playbook update-upgrade
- Jalankan user-create dan hostname-change
- Jalankan Nginx-Install


## Install Docker seluruh node
- ansible-playbook docker-install.yml

## App
### Git Clone

- Jalankan ssh-keygen
- masukan pubkey ke github
- ansible-playbook ssh-key.yml
- Edit file ansible.cfg dan gunakan user rizal
- ansible-playbook git-clone.yml

### Housy
- ansible-playbook database-setup
- ansible-playbook docker-setup

## Jenkins

- ansible-playbook ssh-key.yml




## Prometheus

### Baru start

- docker-install-node-exporter
- prometheus-install.yml

### Sudah Pernah

- docker-start

## MISC

- docker-prune => hapus
- docker-start => start container


## yang belum

- masukin sequelize migrate