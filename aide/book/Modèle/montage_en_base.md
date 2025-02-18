# Les différentes façons de concevoir la base "StaR-Eau"

Suivant les gestions techniques ou politiques de gestion de base des différents maîtres d'ouvrage ou gestionnaires, le montage en base de données peut revêtir plusieurs possibilités que le standard tente de satisfaire.
Le découpage des fichiers sql d'aide à la création d'une base postgis doivent permettre les différentes solutions.

# Gestion différenciée
## Eau Potable seule
### Service sans la gestion des branchements
ou avec une gestion différenciée des branchements
Le montage ne comporte alors que les tables mères, communes, et les schéma assainissement

![d_montage_base](https://github.com/user-attachments/assets/52ac9c25-b11a-40f0-9835-c37879522d40)

On peut aussi faire la même chose pour un service qui ne gère que les branchements

![c_montage_base](https://github.com/user-attachments/assets/061737fd-90cd-4537-b766-18ae191a043f)

### Service AEP réseau et branchements
Sans doute le plus courant, il existe toutefois 2 possibilités :
1. reprendre les montages ci-dessus en créant 2 bases, ou en renommant les tables mères (exemple : noeud_reseau --> noeud_branchement ou noeud_reseau_brcht...).
2. utiliser les mêmes tables mères.

![b_montage_base](https://github.com/user-attachments/assets/21c99697-fc0a-4794-a239-d6d2e9885db7)

## Assainissement seul
Comme pour l'AEP
### Service sans la gestion des branchements
ou avec une gestion différenciée des branchements

![g_montage_base](https://github.com/user-attachments/assets/fee2307c-6c0a-43d3-883c-6bb6d4d3e6bd)

que les branchements :

![f_montage_base](https://github.com/user-attachments/assets/da6e80d7-fdc3-41f2-9e2e-53c987334c5c)

### Service ASS réseau et branchements

![e_montage_base](https://github.com/user-attachments/assets/0f2a5dcb-e584-495d-b691-4f2f25eaed38)

# gestion combinée

Il peut exister aussi la possibilité de créer un service complet eau et assainissement, qui combine les possibilités ci-dessus, tout en permettant aussi d'avoir des tables mères totalement communes. Le modèle dans base_postgis est monté comme cela pour ne pas surcharger les possibilités dans les fichiers et pour des facilités de modification du modèle.

Les tables mères peuvent être communes à toutes les tables.

![a_montage_base](https://github.com/user-attachments/assets/dcad2bfd-6ede-4f4c-a623-b75c1883b6e8)

On peut aussi réaliser toutes les combinaisons intermédiaires (que réseau avec tables mères communes, que branchement avec table communes, tables mère communes pour réseau et autre tables mère pour les branchements...).

# avantages et inconvénients des montages
Le montage incluant les tables mères identiques permet de mieux gérer les relations entre les éléments hors topographie, cela crée des tables plus légères, facilite l'exportation. Cela peut nécessité la redondance des listes de valeurs communes.

Toutefois, les montages incluant les mêmes tables mères pour toutes les tables peut créer une surcharge, un requêtage et une extraction moins simple.

Le montage recommandé pourrait être le suivant. Il n'y a toutefois aucune obligation et le choix reste de la responsabilités du gestionnaire de la base ou des possibilités techniques.

