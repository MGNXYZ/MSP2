# Création de la VM pfsense


## 1. Paramètres de la machine virtuel.
![image](https://user-images.githubusercontent.com/95431446/175907502-8662c3af-d4a8-458c-8bcb-18d27230da12.png)

## 2. Installation classique de Pfsense

![image](https://user-images.githubusercontent.com/95431446/175908012-6a98ee43-7a6f-4480-9dfe-8c810dd0e615.png)

>Accept

![image](https://user-images.githubusercontent.com/95431446/175908064-ffabad9a-ce2d-47c5-a15e-044d005653ac.png)

>Install

![image](https://user-images.githubusercontent.com/95431446/175908160-a427bf76-0ee1-45fc-b736-a11f51303323.png)

>Auto UFS

![image](https://user-images.githubusercontent.com/95431446/175908351-ced32c73-f629-4d6a-9877-895d6001db77.png)

>No

![image](https://user-images.githubusercontent.com/95431446/175908410-06fe4564-52e7-441c-bb5c-34ff6bfa5bfa.png)

>Reboot

>Fin de l'installation

## 3.Mise en place des interfaces réseaux

- A. On commence par assignés les interfaces réseaux

![image](https://user-images.githubusercontent.com/95431446/175908849-6e30b79c-1e2a-4692-9bd5-398c671935b5.png)

>Sélectionner l'option 1

![image](https://user-images.githubusercontent.com/95431446/175909216-ccb7c77f-6adb-4e9f-8dc3-87449ad2686c.png)

>Sélectionner non pour les VLAN
>Attribuer em0 au réseau WAN
>Attribuer em1 au réseau LAN
>Attribuer em2 au réseau Optional 1
>Enfin validé la configuration avec Y

- B. Maintenant il nous faut assigné les IP a nos interfaces.

![image](https://user-images.githubusercontent.com/95431446/175911315-d3e0a48e-24fa-4406-a88a-ed36b273b086.png)

![image](https://user-images.githubusercontent.com/95431446/175916642-81937771-59ba-49b3-ae16-47d496ca7c70.png)

>Faire le processus pour chaque interface en suivant le plan d'adressage créer précédemment 
>em1 192.168.210.254/24 pas de gateway mettre non au DHCP pas d'IPV6, laissé en HTTPS.
>OPT 1 192.168.213.254/24 pas de gateway mettre non au DHCP pas d'IPV6, laissé en HTTPS.

![image](https://user-images.githubusercontent.com/95431446/175918374-4f93b69e-2ae6-46eb-81c3-700c44dab04a.png)


 
