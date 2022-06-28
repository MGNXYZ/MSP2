# Implémentation d’un service DNS interne

## 1. Implémentation d’un service DNS interne 

- Sur Debian il nous faut installer le paquet Bind9 avec la commande ```apt install bind9```

- Une fois le paquet installer on passe a la configuration en ajoutant une acl à /etc/bind/named.conf a l'aide de nano

![image](https://user-images.githubusercontent.com/95431446/176190569-445c6f1a-3cdb-4c80-be40-40531200d81e.png)

- Ensuite on va configurer un redirecteur inconditionnel dans /etc/bind/named.conf.options encore une fois a l'aide de nano

![image](https://user-images.githubusercontent.com/95431446/176191367-002240fa-59b2-461f-8cb1-3b2538d21673.png)

- On restart et vérifie le status de bind9

![image](https://user-images.githubusercontent.com/95431446/176191803-5a61a3aa-9a9c-4a01-a0b4-7f98351839b9.png)

>En cas d'erreur utilisé la commande named-checkconf

- Renseigner le nouveau serveur DNS sur les serveur windows 

![image](https://user-images.githubusercontent.com/95431446/176192265-3a067b07-622a-44a1-a757-aca21c499682.png)

- On vérifie la résolution des noms de domaine a l'aide de la commande nslookup 

![image](https://user-images.githubusercontent.com/95431446/176192926-aff7715a-2e76-4141-8b0b-d57f11bf769b.png)

![image](https://user-images.githubusercontent.com/95431446/176193418-237abfde-33bd-4d5c-a4c8-bb8a922c5e87.png)

- Pour rendre le service DNS accecible au client il nous faut ajouter une options au serveur DHCP de W19-2

![image](https://user-images.githubusercontent.com/95431446/176194927-0aabf6dd-2e43-468a-a984-520ab8981efe.png)

>Il faut renouveler les baux des clients pour que le changement soit pris en compte

![image](https://user-images.githubusercontent.com/95431446/176195965-aeafef42-4869-4cfb-b81a-6eeb18ea4232.png)

![image](https://user-images.githubusercontent.com/95431446/176196053-ab00fb0a-0a83-4e71-84a4-101917d0e6ca.png)

- Pour le client debian 

![image](https://user-images.githubusercontent.com/95431446/176197141-077e16f6-af43-4c87-8690-c7b428234910.png)

![image](https://user-images.githubusercontent.com/95431446/176197279-dbd09c4a-5a96-4ae9-8ae6-5e5fb2b93e66.png)


## 2. Configuration de la résolution directe d’un espace de noms interne

- On va déclarer la zone directe (et de mes deux zones inverses) dans le fichier /etc/bind/named.conf.local

![image](https://user-images.githubusercontent.com/95431446/176200253-916f20e5-e5e0-4697-9b2c-972373486718.png)

- Création du fichier de zone de recherche db.correction52.infra.tld dans /var/cache/bind

![image](https://user-images.githubusercontent.com/95431446/176202393-c4d450f6-8e34-44e4-8a01-c11894eb6732.png)

- On vérifie le fichier a l'aide de la commande ```named-checkzone correction52.infra.tld /var/cache/bind/db.correction52.infra.tld```

![image](https://user-images.githubusercontent.com/95431446/176202468-8ec1fb94-6f74-42fa-9976-093b052e9adc.png)

- On va maintenant restart bind9 ```systemctl restart bind9```

- Nous allons également tester la résolution sur notre client windows a l'aide de nslookup

![image](https://user-images.githubusercontent.com/95431446/176211251-7767c6e6-8bca-4d87-9617-c8b641271c2c.png)

- Et sur le client linux a l'aide de dig

![image](https://user-images.githubusercontent.com/95431446/176211992-03e7e7f5-54aa-4cad-ac1a-a2730ee24648.png)

## 3. Configuration de la résolution inverse

- On créer les fichiers de zone de recherche inverse db.208.168.192.inv et db.211-168-192.inv dans le dossier /var/cache/bind

![image](https://user-images.githubusercontent.com/95431446/176222003-6b266753-be3e-4fe1-87c9-c15cf17139ae.png)

![image](https://user-images.githubusercontent.com/95431446/176222085-6d4a54ce-7e03-4199-b348-3d402ba42b4a.png)





