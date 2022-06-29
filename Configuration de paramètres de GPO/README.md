# Configuration de paramètres de GPO

## 1. Ajout d'un wallpaper général

- On ouvre l'outils Gestion des stratégies de groupe

![image](https://user-images.githubusercontent.com/95431446/176438072-f99fdeca-9af4-4793-8c16-115c922f03a7.png)

>Forêt > Domaines > ****.domaine.tssr > Objets de stratégies de groupe > Nouveau

![image](https://user-images.githubusercontent.com/95431446/176439174-5dcf36dd-964a-402b-a287-5573514eca37.png)

![image](https://user-images.githubusercontent.com/95431446/176440831-a472c471-eddc-4447-9892-e06f72d34ff9.png)

![image](https://user-images.githubusercontent.com/95431446/176441048-367205e0-e77e-4dd0-aee3-517269a67f0b.png)

> Configuration Utilisateur > Stratégies > Modèles d'administration > Bureau > Bureau > Papier peint du bureau

![image](https://user-images.githubusercontent.com/95431446/176441314-28de4f9c-f12f-45d2-b274-d6a04147bacb.png)

>//srvw2.mugen.domaine.tssr/PapierPeint$/corp.jpg

- Nous allons maintenant créer un fichier partager a la racine de F: contenant notre wallpaper corp.jpg

## 2. Modification du mot de passe obligatoir sous 30 jours

![image](https://user-images.githubusercontent.com/95431446/176444795-593fe0da-9e46-4454-a532-009ad8fc24c1.png)


![image](https://user-images.githubusercontent.com/95431446/176445381-1e93c7dd-3fee-4032-a501-5194e079069b.png)

## 3. Les secrétaires verront automatiquement le partage SERVICES apparaitre dans leur explorateur de fichiers

![image](https://user-images.githubusercontent.com/95431446/176446680-bfc8c6f9-b06c-4237-be7f-7eff0423999f.png)

![image](https://user-images.githubusercontent.com/95431446/176446752-58cf1541-a46a-4e31-9a74-838cd5fae5e3.png)

![image](https://user-images.githubusercontent.com/95431446/176490757-d3db26e5-c223-45ed-9967-e6d4610938ab.png)

![image](https://user-images.githubusercontent.com/95431446/176490851-96d7fa52-2efb-4ff0-b5b0-3330d23fb4de.png)

![image](https://user-images.githubusercontent.com/95431446/176490931-6795df84-2eb6-48c6-9118-96470fc7c908.png)

![image](https://user-images.githubusercontent.com/95431446/176491358-3c3d7e83-fab1-486e-ab5c-01cb5a81d19a.png)

## 4. Seul un administrateur de la machine pourra installer ou mettre à jour les pilotes de périphériques.

- Nouvel objet de stratégie de groupe InstallDrivers liée à la racine du domaine 

![image](https://user-images.githubusercontent.com/95431446/176493468-7053c654-faf5-41ed-80c2-64c820233cb5.png)

![image](https://user-images.githubusercontent.com/95431446/176494520-959e6ba7-3684-4fe0-b1a3-af5a59d7265b.png)

>Configuration Ordinateur > Stratégies > Modèles d'administration > Système > Installation de périphériques > Restrictions d'installation de périphériques

- Empêcher le redémarrage automatique des postes en cours d’utilisation

![image](https://user-images.githubusercontent.com/95431446/176495264-a09dbf34-d8e5-4877-b702-f7703f78fd35.png)

Configuration Ordinateur > Stratégies > Modèle d'administration > ComposantWindows > Windows Update > Pas de redémarrage automatique avec des 
utilisateurs connectés pour les installations planifiées de mises à jour automatique

-  Lors de recherches Windows, ne pas rechercher sur Internet

![image](https://user-images.githubusercontent.com/95431446/176496192-14a025c7-40d9-4e29-80bd-55b7f4fe3778.png)

>Configuration Ordinateur > Stratégies > Modèle d'administration > Composant Windows > Rechercher

- Bloquer la remontée d’erreurs à Microsoft

Configuration Ordinateur > Stratégies > Modèle d'administration > Système > Gestion de la communication Internet > Paramètres de communication Internet >
Désactiver Rapport d'erreurs Windows

![image](https://user-images.githubusercontent.com/95431446/176497377-235677ea-2a8c-4241-9a09-bfdc9426daaa.png)

# FIN
