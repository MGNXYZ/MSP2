# Création d'un domaine Active Directory

## 1. Installation du service ADDS sur Windows Server 1

- Depuis la console de gestion du serveur > Gérer > Ajouter des rôles et des fonctionnalités

![image](https://user-images.githubusercontent.com/95431446/176231391-e874f376-9f6f-432a-a607-9a17bb35dccf.png)

![image](https://user-images.githubusercontent.com/95431446/176231460-0cec19d8-5c4c-4461-8c9b-6743f058fb4f.png)

![image](https://user-images.githubusercontent.com/95431446/176231526-6cfbc63c-5961-45da-ae9e-530900df9ab0.png)

![image](https://user-images.githubusercontent.com/95431446/176231678-12aff7af-907f-4b99-a434-b45ffd11410b.png)

![image](https://user-images.githubusercontent.com/95431446/176232137-174f762a-02b0-463c-b9f8-b401e61444eb.png)

![image](https://user-images.githubusercontent.com/95431446/176232320-d9eae6f9-1f0d-4354-8c4c-685ad8d8483a.png)

![image](https://user-images.githubusercontent.com/95431446/176232881-4e304feb-00a1-4fc1-b85a-8a5b0dbaa676.png)

![image](https://user-images.githubusercontent.com/95431446/176233060-e2d5059f-8211-4e3c-b9a6-d23cfa541286.png)

![image](https://user-images.githubusercontent.com/95431446/176233197-79093e68-0bf3-4db1-ab40-3a7dea9d92ad.png)

![image](https://user-images.githubusercontent.com/95431446/176233383-03cda3d4-9308-459f-a59e-2674f815b5b6.png)


## 2. Étude de la nouvelle zone DNS suite à la création du domaine Active Directory

Avant l'intégration au domaine, il faut que les clients puissent résoudre les enregistrements SRV du domaine DNS en lien avec l'Active Directory.
Ça n'est pas le cas pour le moment. Il faut en prérequis créer un redirecteur conditionnel vers la zone DNS du domaine Active Directory

- On ce rend sur notre serveur DNS debian et on modifie /etc/bind/named.conf.local

## 3. Intégration du poste Client Windows au domaine Active Directory

- On ouvre ```sysdm.cpl```

![image](https://user-images.githubusercontent.com/95431446/176242640-ce31b653-8ed6-4cc0-8722-45ee34c9c026.png)

![image](https://user-images.githubusercontent.com/95431446/176242740-2fc7c1de-3d76-4daf-af52-9505060dabc8.png)

![image](https://user-images.githubusercontent.com/95431446/176242861-7b99ec53-575d-4dbc-b2d3-a4ed09a6be40.png)

![image](https://user-images.githubusercontent.com/95431446/176244792-9af4179b-9ae0-4242-9713-b8557b340075.png)

![image](https://user-images.githubusercontent.com/95431446/176244886-9777c491-4858-4032-b328-549a59c8e30c.png)

- Répeter l'opération sur WS19-2


