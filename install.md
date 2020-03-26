# VM config
- 1 proco, 2 coeurs
- 4gb de RAM
- disque 50gb
- carte réseau: bridged

OS: debian 10  
default install with general system utilities

# Dépendances

vim  
sudo  
openssh-server

# Firewall

    # apt install ufw
    # ufw allow 22
    # ufw allow 80
    # ufw allow 443

# SQL

    $ apt-get install mariadb-server -y

    mysql_secure_config

Change root password : no
Remove anonymous user : yes
Disallow root login remotely : yes
Remove test database ... : yes
Reload privilege table now : yes

    vim /etc/mysql/mariadb.conf.d/50-server.cnf

Mettre les lignes suivantes en commentaire :

    #skip-external-locking
    #bind-address = 127.0.0.1

Ajout d'utilisateur admin:

    mariadb  
    CREATE USER maria@'%' IDENTIFIED BY 'maria';

Redémarer le serveur