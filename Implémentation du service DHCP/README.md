# Mise en place du service DHCP

# 1. Installation du serveur DHCP sur windows server 2

- On ce rend sur le gestionnaire de serveur > Gérer

![image](https://user-images.githubusercontent.com/95431446/176165988-2a5e39fb-6cd2-462b-b1e0-df4cad3e0ab5.png)

- Ajourer des rôles et fonctionnalités

![image](https://user-images.githubusercontent.com/95431446/176166143-c0909c71-91c4-4392-892e-e63367528bf7.png)

![image](https://user-images.githubusercontent.com/95431446/176166330-ea5a1b37-754c-4531-9f32-cdda2f21ee8a.png)

![image](https://user-images.githubusercontent.com/95431446/176166435-d632b3aa-c684-4368-b6ae-6070e40948ea.png)

![image](https://user-images.githubusercontent.com/95431446/176166492-8fc09ec9-33fc-4fd7-a80a-976fec748134.png)

![image](https://user-images.githubusercontent.com/95431446/176166566-b5d17c2d-99d6-4e74-a52e-50fd88c78836.png)

![image](https://user-images.githubusercontent.com/95431446/176166628-6996a658-4f7a-4e1f-ae5c-7ff1d8dcc37a.png)

![image](https://user-images.githubusercontent.com/95431446/176166672-eb191bc2-f7f1-4deb-9ac9-b6ebae0d7fae.png)

![image](https://user-images.githubusercontent.com/95431446/176166789-dff1803d-9909-46a9-98bd-940b2b369baf.png)

![image](https://user-images.githubusercontent.com/95431446/176166903-2874ad93-efce-4e04-8edd-a662c4399024.png)

- Une fois l'installation terminé ce rendre sur le petit drapeau en haut a droite 

![image](https://user-images.githubusercontent.com/95431446/176173923-987f3100-2e40-4aaa-a465-d26ec3b28466.png)

![image](https://user-images.githubusercontent.com/95431446/176173975-46e0d0c0-1fed-4fb4-8d8c-c8b303e75d5b.png)

![image](https://user-images.githubusercontent.com/95431446/176174021-a2a15cbe-5b8a-4001-8936-0107e84e3221.png)

- Dans le menu démarrer cliquer sur outils d'administration 

![image](https://user-images.githubusercontent.com/95431446/176174154-84c807ef-309a-41de-913d-0e5d13bb5f6c.png)

- Puis double clic sur DHCP

![image](https://user-images.githubusercontent.com/95431446/176174219-dce3f551-2b33-41f9-8024-5cd66e37b170.png)

- Clique droit sur IPV4 > Nouvelle étendue...

![image](https://user-images.githubusercontent.com/95431446/176175653-5607f042-e579-4493-af12-2b5028c6f403.png)

![image](https://user-images.githubusercontent.com/95431446/176176223-9a58086b-fcd5-41bc-b198-daa0c2c9a45c.png)

![image](https://user-images.githubusercontent.com/95431446/176177055-f07bcb47-bb1d-40d1-bd2e-2f82dd8615a2.png)

>L'étendu souhaiter

![image](https://user-images.githubusercontent.com/95431446/176177159-7464aa94-3354-4469-ada8-b530702ef2d5.png)

![image](https://user-images.githubusercontent.com/95431446/176177443-753e5267-d826-4a08-a5c1-e96becefb03f.png)

>Baille de 8 jours

![image](https://user-images.githubusercontent.com/95431446/176177512-27009175-37e6-4e11-abca-416c9a55861f.png)

![image](https://user-images.githubusercontent.com/95431446/176177631-d3c250e5-97d0-4402-9a61-29e3c4325124.png)

- On va maintenant ajouter une option pour attribuer l'adresse IP du routeur

![image](https://user-images.githubusercontent.com/95431446/176178173-0ba91a42-ff44-4be3-a155-137d2adc67e4.png)

![image](https://user-images.githubusercontent.com/95431446/176178448-46fca028-7527-42d4-a487-15fb1965df5c.png)

- Nous activons enfin l'étendu en fessant clique droit sur celle si puis activé

![image](https://user-images.githubusercontent.com/95431446/176178657-f55019dc-dd6e-41ca-9e59-40e00157208c.png)


## 2. Installation du DHCP serveur sur la machine DEB-S1

- On commence par télécharger le paquet isc-dhcp-server

- On va ensuite configurer l'interface d'écoute dans /etc/default/isc-dhcp-server avec l'éditeur nano

![image](https://user-images.githubusercontent.com/95431446/176179968-72d980cf-785f-4726-975c-a35303bf671d.png)

>On ajoute a INTERFACESv4 ens33

- Il nous faut maintenant configurer le service, à travers son fichier de configuration /etc/dhcp/dhcpd.conf à nouveau nous utiliserons nano

![image](https://user-images.githubusercontent.com/95431446/176182560-5f603cb8-b6ff-484f-a559-e0bf61d014c5.png)

- On va maitnenant vérifier que tout fonctionne a l'aide de la commande ```dhcpd -t```

![image](https://user-images.githubusercontent.com/95431446/176182648-1c6fe592-562b-4251-b642-efaa18e59852.png)

>Aucune erreur a déplorer

- On lance donc le DHCP avec la commande ```systemctl start isc-dhcp-server```

- On vérifie ensuite le status a l'aide de la commande ```systemctl status isc-dhcp-server```

![image](https://user-images.githubusercontent.com/95431446/176183089-e7710fb5-3be4-48f0-a16f-ad35f961d096.png)

## 3. Configuration du relais DHCP sur le routeur pfSense

- Sur l'interface Pfsense ce rendre sur services > DHCP Relay

![image](https://user-images.githubusercontent.com/95431446/176183554-e5ef3b16-0102-4352-b73e-45e18cf5ee88.png)

- On test maintenant le DHCP sur nos différents clients

![image](https://user-images.githubusercontent.com/95431446/176185422-f992bbdd-1990-4606-b71c-339f5f467254.png)

![image](https://user-images.githubusercontent.com/95431446/176185545-2b1d3990-b8b5-4025-991c-532cd247d7ea.png)

![image](https://user-images.githubusercontent.com/95431446/176185634-2a6080e5-0345-4f41-bcc4-20190b679d1c.png)

- Sous windows 

![image](https://user-images.githubusercontent.com/95431446/176186408-be120bcc-e871-4406-9898-5f3d24f66ad0.png)

![image](https://user-images.githubusercontent.com/95431446/176186568-adce81eb-312b-4000-82f2-cdf53e46a36c.png)

![image](https://user-images.githubusercontent.com/95431446/176186625-3731725b-91e8-4642-8b4b-b2ae5b524a5e.png)

### FIN
