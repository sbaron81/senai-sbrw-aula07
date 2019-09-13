# Atividade

1) Criar uma VM com Ubuntu Server
---

CPU: 2
Mem: 2GB
Disco: 20GB
Rede: 2 placas 
       - NAT 
       - Host-only
Obs: Deverá ter conectividade a internet a ao windows de vocês

2) Acessar a console e verificar o endereço IP

Comando:
```
$ ip add
```

- Anotem os dois enderços IPs


3) Atualizar a lista de pacotes do Ubuntu

Comando:
```
$ sudo apt-get update
```

4) Instalar o Samba server

Comando:
```
$ sudo apt-get install samba
```

5) Verificar se o samba foi instalado

Comando:
```
$ sudo systemctl status smbd
```

6) Criar o diretório que desejamos compartilhar

Comandos:
```
$ sudo mkdir /arquivos
$ sudo chmod 777 /arquivos
```

7) Configurar o Samba [samba.conf]

Utilize um editor, como o nano ou vi, por exemplo, e configure o arquivo /etc/samba/smb.conf conforme abaixo:


```
[global]
      netbios name = UbuntuServer
      workgroup = Senai

     security = user
     map to guest = bad user


[arquivos]
     comment = Arquivos temporarios
     path = /arquivos
     guest ok = yes
     read only = on
```

8) Validar se as configurações estão corretas

Comando: 
```
$ testparm
```

9) Adicionar o usuario ao samba

Comando:
```
$ sudo smbpasswd -a NomeDoUsuário
```

Obs: esse usuário deve existir no linux. É possível criar mais usuários, só precisam criar no linux primeiro
Exemplo: 
```
$ sudo adduser usuario2
$ sudo smbpasswd -a usuario2
```
10) Reiniar o Samba

Comando:
```
$ sudo systemctl restart smbd
$ sudo systemctl status smbd
```

11) Testar o acesso ao compartilhamento

- Da máquina de vocês abram o Windows Explorer e digitem
```
\\192.168.56.104\arquivos   
```

Obs: Troquem o IP pelo IP da VM de vocês



  [samba.conf]: https://github.com/sbaron81/senai-sbrw-aula07/blob/master/smb.conf
