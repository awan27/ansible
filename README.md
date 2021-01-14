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


# Cara Pakai

Jalankan 1 => 2 => 0

## 0.semua host [universal, rizal]

- config dengan angka `0` dan `all` harus dijalankan di semua node dengan user rizal,semuanya merupakan dependansi semua aplikasi

## 1.user [universal, ubuntu]

- config dengan angka `1` untuk membuat user dan merubah hostname semua node

## 2.ssh [universal, ubuntu]

- generate key, lalu pindahkan private key dan pub key ke folder ansible
- setting `2.ssh-key` dengan private key dan pub key yang telah dibuat tadi
- jalankan

## 3.database [?]


## 4.deployment [housy, rizal, ubuntu]

- untuk pertama install jalankan `4.deployment-apps-setup.yml` [frontend dan backend node]
- jika sudah pernah setting, jalankan `4.deployment-apps-start.yml` [frontend dan backend node]
- untuk build image jalankan `4.deployment-apps-build.yml`

- untuk clone repo jalankan `4.deployment-apps-clone.yml`


## 5.cicd [universal]

- untuk pertama install jalankan `5.cicd-jenkins-setup.yml` [jenkins node]
- jika sudah pernah setting, jalankan `5.cicd-jenkins-start.yml` [jenkins node]

## 6.monitoring [universal]

- untuk pertama install jalankan `6.monitoring-node-exporter.yml` dan `6.monitoring-prometheus-install.yml`
- jika sudah pernah setting, jalankan `6.monitoring-all-start`