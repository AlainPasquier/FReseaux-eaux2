`ASS` `ass_raccord` :link: `noeud_reseau`

Les raccords sont les pièces qui permettent la connexion entre la canalisation de branchement et la canlisation principale.
**Ils ne sont pas topologiques, non coupants ou non sécants, avec la canalisation principale**

# type de raccords

## piquage direct

piquage consiste à percer le collecteur à un diamètre correspondant à celui du branchement

![source DDTM](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTgH_unCVDsiZtZbhw6SHjQ30sIJf7n27yfGA&s)

## culotte

Culotte en forme de Y

![source www.soval.fr](https://www.soval.fr/wp-content/uploads/2018/02/SOUPL-T-ASS-CULOTTE-EEE.png)

## té de branchement

culotte de branchement en forme de T

## selle de piquage

![Source nicoll](https://www.nicoll.fr/sites/default/files/styles/variation_product_carousel_mobile/public/products/47361.jpg.webp?itok=-i_Ud7Pf)

## tulipe de piquage

![source https://www.norham.fr/](https://www.norham.fr/upload/miniatures/3334/1000/photo-tulipe-de-piquage-tflex-montage.jpeg)

# référence à la canalisation principale

Il est conseillé d'utiliser la référence unique issue de la table mère canalisation.
Ceci permet de localiser et de répertorier rapidement les branchements présents sur les tronçons de canalisation.

> [!tip]
> une requête simple permet de connaître le nombre de branchements sur un tronçon.

```sql
SELECT ref_canalisation, COUNT(1) FROM ass_raccord GROUP BY ref_canalisation
```
