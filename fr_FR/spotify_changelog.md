# 28-06-2024

- Refonte de la sécurité et configuration 
- Refonte de la partie cast v2

# 02-11-2024

- Correctif sur le reveil des appareils castv2 pour inhiber le broadcast

# 25-10-2023

- Correctif sur le reveil des appareils castv2 avec encore des modifs d'authentification de Spotify

# 20-03-2023

- Correctif sur le reveil des appareils castv2 avec le nouveau système d'authentification de Spotify

# 03-01-2023

- Correctif sur arrêt démon suite à une erreur 503 de l'API spotify
- Renommage d'une classe CastMessage en CastMessageSpotify pour compatibilité avec le plugin Gcast

# 02-01-2023

- Mise à jour du reveil des appareils castv2 avec le nouveau système d'authentification de Spotify

# 25-03-2022

- Centralisation de la documentation

# 24-03-2022

- Correction de problème d'affichage sur le tableau du plugin

# 24-09-2021

- Reveil des appareils castv2 avec le nouveau système d'authentification de Spotify

# 26-04-2021

- Correction du refreshToken en https 

# 16-04-2021

- Correction setCredentialsError() liées à priori à des incompatibilités suite des évolutions de l'API spotify 
- Diminution du nombre d'appel externe à l'API spotify (toutes les secondes pour le statut et devices / toutes les minutes pour les playlists, pas configurable pour l'instant mais ça viendra)

# 13-04-2020

- Correction d'un bug dans le cas de context null, 
 
# 17-03-2020

- Prise en compte du nouveau get_token pour la connexion castv2
- Correction d'un problème de refresh du flag de lecture aléatoire avec plusieurs équipements.

# 12-02-2020

- Ajout du mode play automatiquement sur selection d'un device, y compris lors d'un device cast v2

# 22-01-2020

- Corrections d'un décalage d'image au niveau widget remontée via le forum

# 22-12-2019

- Optimisation de l'authentifcation pour la lecture sur les équipements google cast V2.

# 11-11-2019

- Correction d'un problème suite à des tests avec plusieurs équipements
- Correction d'un problème de refresh token intempestifs depuis le daemon 

# 23-10-2019

- Correction d'un probléme de compatibilité de navigateur sur la fonction tokenize

# 22-10-2019

- Mutualisation des clés entre le widget et le daemon

# 21-10-2019

- Correction d'un problème sur refresh token de spotify connect API

# 20-10-2019

- Ajout du support des devices compatibles castv2 
- Corrections de bugs

# 17-09-2019

- Prise en compte du nouveau mécanisme de widget de la V4
- Extension à toutes les playlists (pas uniquement les privées)
- Adptation du thème de l'IHM de configuration à la V4
 
# 15-09-2019

- Initialisation du shuffling à false sur le widget
- Correction d'un défaut d'affichage sur la liste des équipements

# 12-09-2019

- Mise en conformité par rapport aux règles de codage jeedom

# 11-09-2019 

- Mise à jour de la documentation

# 10-09-2019

- Correction d'un bug lorsqu'il y a plus de 10 playlists

# 05-06-2019

- Ajout de la possibilité d'utiliser l'acces jeedom http
  
# 22-05-2019

- Version initiale publiée sur le market

