# Redondance des principaux services

## 1. Ajout d’une nouvelle instance du service DHCP

- Sur Debian Server, installation du paquet isc-dhcp-server

- Il faut configurer l'interface d'écoute dans /etc/default/isc-dhcp-server

![image](https://user-images.githubusercontent.com/95431446/176498437-c8b91f6f-63a9-4fac-abbc-fa2c85f5f2d6.png)

- Il faut maintenant configurer le service, à travers son fichier de configuration /etc/dhcp/dhcpd.conf

![image](https://user-images.githubusercontent.com/95431446/176499349-ebb81afd-b6b4-46da-b5e5-94d16d00394f.png)

>dhcpd -t pour vérifier la configuration

![image](https://user-images.githubusercontent.com/95431446/176499520-dc909a40-64a0-4498-bae0-ef245a3999d2.png)

- On démarre le DHCP a l'aide de la commande ```systemctl start isc-dhcp-server``` puis ```systemctl status isc-dhcp-server```

![image](https://user-images.githubusercontent.com/95431446/176499872-864ef574-5c44-4b72-92ca-f2ca50b03a76.png)

- Configuration du service relais DHCP sur pfSense

![image](https://user-images.githubusercontent.com/95431446/176500275-44591d9a-92a0-4cf9-9222-dbd6916f73d9.png)

- Tester le bon fonctionnement du serveur DHCP de secours

>Avec l'un de vos clients, relâcher le bail en cours
>Sur Windows Server 2, arrêter le service du serveur DHCP principal.
>Avec ce même client, demandez un nouveau bail. Vous devriez récupérer un bail du serveur de secours

![image](https://user-images.githubusercontent.com/95431446/176502169-e6937ebb-22dc-4e9d-b37b-5f4b7d36c4df.png)

## 2. Ajout d’un second serveur DNS

- Sur Windows Server 2, installation du rôle DNS

![image](https://user-images.githubusercontent.com/95431446/176504636-46167748-763b-451f-b60f-daf3786fec4a.png)

![image](https://user-images.githubusercontent.com/95431446/176504999-e12a0e39-0513-41d5-b39b-383f90b33d94.png)

![image](https://user-images.githubusercontent.com/95431446/176505209-c31e5447-4237-40c1-9c73-f32e5ef80703.png)

![image](https://user-images.githubusercontent.com/95431446/176505700-ca645552-c85c-4c48-94e7-cbc6e368eaa3.png)

![image](https://user-images.githubusercontent.com/95431446/176505758-99c36085-0419-4108-aed4-27abd79b0b35.png)

- Création d'un redirecteur conditionnel

>Clic droit sur le nœud Redirecteurs conditionnels > Nouveau redirecteur conditionnel

![image](https://user-images.githubusercontent.com/95431446/176505913-416c4afe-e229-459a-8887-f53b36c0f532.png)

![image](https://user-images.githubusercontent.com/95431446/176506230-c71c7df1-d826-4dc5-8250-bafb6f652918.png)

- Création de la zone secondaire pour le domaine correction52.infra.tld

>Dans la console DNS, clic droit sur zone de recherche directes > Nouvelle Zone

![image](https://user-images.githubusercontent.com/95431446/176506612-2e92076f-4acd-49e0-8cba-15941b753566.png)

![image](https://user-images.githubusercontent.com/95431446/176506717-a1aebf8b-fdd6-4a0f-8f7b-5614a3cff002.png)

![image](https://user-images.githubusercontent.com/95431446/176506854-54e20e60-ecf8-48c6-b2fc-d41c87d1f39d.png)

![image](https://user-images.githubusercontent.com/95431446/176506889-58d1330f-0934-4380-8287-2fb311cd7465.png)

- Sur Debian Serveur, dans la zone DNS ajouter un enregistrement NS correspondant au nom du serveur Windows Server 2

>Sur le fichier /var/cache/bind/db.correction52.infra.tld ajouter la ligne NS suivante

![image](https://user-images.githubusercontent.com/95431446/176507358-e121f277-7d0e-44a2-92d2-cb5006278bd8.png)

>Redémarrez le service bind9 ```systemectl restart bind9```

-  Sur Debian Serveur, autoriser les transferts de zone vers Windows Server 2

- Dans le fichier /etc/bind/named.conf.local ajouter la directive allow-transfer avec l'adresse IP de votre serveur DNS secondaire

![image](https://user-images.githubusercontent.com/95431446/176508020-c9062c43-054c-45e6-aeb8-64a5b0c81e3e.png)

>Redémarrez le service bind9 ```systemectl restart bind9```

- Sur Windows Server 2, dans la console DNS raffraichir l'affichage 

![image](https://user-images.githubusercontent.com/95431446/176509741-3d3d0d00-fdcd-489f-a416-a8bd8b90ed2e.png)


