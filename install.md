# VM config


# Dépendances

vim
sudo

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