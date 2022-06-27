# Création des VM serveur

## 1. Création de la machine DEB-S1 sous debian 11

![image](https://user-images.githubusercontent.com/95431446/175919945-856dc232-5f4e-4d28-a769-96ddae812da5.png)

>On utilisera les réglages si dessus.

>Finaliser l'installation puis configuré le réseau

- On ce modifie le fichier interfaces situé dans /etc/network/interfaces a l'aide de nano

![image](https://user-images.githubusercontent.com/95431446/175922352-d65cb0db-9d62-4255-b762-8100b71d4126.png)

- On redémarre ensuite le network a l'aide de la commande ```systemctl restart networking```

![image](https://user-images.githubusercontent.com/95431446/175922617-d774dee8-e649-45a3-87a8-a93335161967.png)

## 2. On passe ensuite à la création des VM windows serveur.

![image](https://user-images.githubusercontent.com/95431446/175923278-e2e2ecda-14ee-4b7e-a313-37cc4d7d7a93.png)

>Utilisé cette configuration

>Une fois l'installation terminer mettre en place l'IP static 192.168.210.101/24 avec la gateway 192.168.210.254

![image](https://user-images.githubusercontent.com/95431446/175938116-2a6e6c6e-35da-4e4e-a43a-5d061b9a8dc7.png)

>On répète l'opération avec WS19-2 192.168.210.102/24 avec la gateway 192.168.210.254

![image](https://user-images.githubusercontent.com/95431446/175937835-e20a7b96-9938-4ecc-b54b-b5c5bacdc537.png)

- On va maintenant essayé de joindre les machines du réseau a l'aide d'un ping

![image](https://user-images.githubusercontent.com/95431446/175939159-1ca3c75e-3560-4ef3-a32b-5b5b0e206f82.png)

>Depuis Debian

![image](https://user-images.githubusercontent.com/95431446/175939328-e09af6aa-7214-4662-9bdf-dc79d83fc8c3.png)

>Depuis Windows server 1

![image](https://user-images.githubusercontent.com/95431446/175939527-800677fa-4c7c-46e7-a50b-902b3a786690.png)


