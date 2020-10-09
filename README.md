# Docker-Compose-Zabbix
 
Este repositório visa forncer uma maneira simples de executar um Zabbix Server utilizando Docker.

## Instalando dependencias:

### Instalando docker
```shell
$ sudo apt-get update

$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
### Add Docker’s official GPG key:
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
apt-key fingerprint 0EBFCD88
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```
### Install Docker Engine
```shell
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
sudo apt install docker-compose

````

### Baixando o repositório do projeto

```shell
cd /opt/
git clone git@github.com:Reisvmr/ZABBIX_DOCKER.git
cd ZABBIX_DOCKER
```

### Criando persistencia para os dados
```bash
mkdir -p ./zbx_env/usr/lib/zabbix/externalscripts \
./zbx_env/etc/zabbix/zabbix_agentd.d \
./zbx_env/var/lib/zabbix/modules \
./zbx_env/var/lib/zabbix/enc \
./zbx_env/var/lib/zabbix/snmptraps \
./zbx_env/var/lib/mysql
```
### Iniciando o Zabbix com Docker compose
```shell
docker-compose up -d --build
```

### Acessando o zabbix

Para acessar o zabbix utilize 

http://ip_do_seu_servidor:80
Usuário:Admin
Senha:zabbix
