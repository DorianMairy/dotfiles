
# Apache
___


## Installation


```sh
apt install apache2
```
### Oui c'est tout !

## Pour relier le nom de domaine il faut aller dans le fichier config d'apache

```sh
cd /etc/apache2/sites-enabled/
nano 000-default
```

### Changer :

            ServerName => nom.de.domaine (ou sous domaine ex panel.monsiteweb.com)
            ServerAdmin => adressemail
            DocumentRoot => dossierdusite

## Mise en place d'un certificat SSL

### les commandes pour installer certbot (ssl gratuit)

#### Assurez-vous que votre version de snapd est à jour

```sh
sudo snap install core; sudo snap refresh core
```

#### Installer Certbot

```sh
sudo snap install --classic certbot
```

#### Préparer la commande Certbot

```sh
sudo ln -s /snap/bin/certbot /usr/bin/certbot
```

## Choisissez comment vous souhaitez exécuter Certbot 

### Soit obtenir et installer vos certificats... 

```sh
sudo certbot --apache 
```

### Ou, obtenez simplement un certificat 

```sh
sudo certbot certonly --apache
```

## Testez le renouvellement automatique 
```sh
sudo certbot renew --dry-run
```
