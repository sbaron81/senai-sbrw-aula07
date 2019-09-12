Lista de atividades

1) Criar uma VM com Ubuntu Server

CPU: 2
Mem: 2GB
Disco: 20GB
Rede: 2 placas 
       - NAT 
       - Host-only
Obs: Deverá ter conectividade a internet a ao windows de vocês

2) Acessar a console e verificar o endereço IP

Comando:
$ ip add

- Anotem os dois enderços IPs

3) Atualizar a lista de pacotes do Ubuntu

Comando:
$ sudo apt-get update

4) Instalar o Samba server

Comando:
$ sudo apt-get install samba

5) Verificar se o samba foi instalado

Comando:
$ sudo systemctl status smbd

6) Configurar o Samba

Comando:
$ sudo vi /etc/samba.conf

Obs: verifique o arquivo exemplo samba.conf aqui no github

7) Validar se as configurações estão corretas

Comando: 
$ testparm


