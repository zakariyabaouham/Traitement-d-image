# Traitement d'image

## Différence entre capteur CCD et capteur CMOS

`Le capteur d’image` est l’un des composants majeur qui influe sur la qualité d’une caméra. Il assure la transformation des signaux lumineux en signaux électriques. En vidéo surveillance, on trouve deux technologies : le capteur CCD (Charged Coupled Device) et le capteur CMOS (Complementary Metal Oxide Semiconductor)

`La technologie CCD` a été spécialement développée, il y a plus de 20 ans pour `le cinéma`, et donc pour `l’industrie des caméras`.

Il est de meilleur qualité qu’un capteur CMOS notamment au niveau de sa sensibilité à la lumière qui permet un meilleur rendu d’image même en sous-exposition.


`La technologie CMOS` a été créée pour s’intégrer dans `des ordinateurs`, elle est plus simple et plus récente.

Elle arrive aujourd’hui à maturité et la qualité du rendu se rapproche de la technologie CCD.

## D’autres facteurs jouent sur la qualité

En conclusion, on peut dire que `la technologie CMOS` (plus récente) arrive à maturité mais que, dans le domaine particulier des caméras de videosurveillance, elle n’égale pas (encore) `la technologie CCD` en terme de sensibilité et de rendu qualitatif de l’image.

A noter que la qualité des images vidéo est aussi liée à la qualité de l’objectif et aux technologies associées : contrôle amplification (AGC) , logiciel de compensation de blanc (AWB), gestion automatique des contre jours (WDR).


# Cours Traitement d'Image:
## Introduction

- `Le Traitement d'image` est les opérations qu'on peut réaliser sur `les images`.
- Avant de `traiter` les images il faut réaliser d'abord ces images, c'est l'étape de `l'acquision` qui consiste à transformer les vues réelles en des images `numériques`
- Après cette étape il faut transformer ces images en `des matrices` qu'on peut traiter par la suite.

![intro](https://user-images.githubusercontent.com/38400126/90697092-83e38b00-e275-11ea-981a-4a5a4720895d.png)

ça c'est les `vues réelles` donc il faut transformer en des images numériques c'est ça l'étape de `l'acquisition` puis `traitement`: c'est `le traitement d'image` donc `le filtrage`, on peut réduire `le bruit`, calcul du `gradient` on va voir ça par la suite, `la détéction des contoures` etc..., et il ya le codage et la `compression` (compression des images et la transmission, l'amélioration, la segmentation etc... 

## L'utilisation de traitement d'image:

- Vision médicale 
- Les images médicales
- Intelligence artificielle
- La reconnaissance des formes ( par ex: `la reconnaissance des visages`)

## Numérisation:

![Num](https://user-images.githubusercontent.com/38400126/90697647-c6f22e00-e276-11ea-82e2-28468fd15ede.png)

 C'est quoi `la numérisation?` c'est transformer les images en des images numériques.
 donc c'est quoi les `images numériques?` les images numériques qu'on peut transformer en `des matrices` la matrice c'est ça.
 - On a l'axe des x et l'axe des y . `Cette matrice` c'est l'image et chqaue `pixel` (chaque case dans cette matrice) avoir une valeur, cette valeur s'appelle `l'intensité`. Cette instensité c'est la valeur du couleur de cette case etc...
 
## Echantillonnage:

- C'est le procédé de discrétisation spatiale d'une image consistant à associer à chaque zone rectangulaire R(x,y) d'une image continue une unique valeur (x,y).
`par exemple dans cette matrice (au-dessus) cette intensité prend une seule valeur (unique on peut pas avoir plusieurs valeurs en même temps c'est illogique)`

## Quantification:

- Désigne la limitation du nombre de valeurs différentes que peut prendre I(x,y).
`par exemple: Cette intensité peut comprendre la valeur compris entre 0 et 255, on ne peut pas dépasser 255 par exemple cette image en nvieau de gris.`

`Une image numérique est une image échantillonnée et quantifiée.`

## Pixels et niveaux de gris 

![pixels](https://user-images.githubusercontent.com/38400126/90699442-323dff00-e27b-11ea-9b03-f33afe67d6dc.png)

 ça c'est une image (Largeur et Hauteur), c'est une matrice. `cette case d'abord s'appelle le pixel[i,j]`, ce pixel prend une valeur qui s'appelle `l'intensité` (c'est la valeur de pixel) 
 
 ![codage](https://user-images.githubusercontent.com/38400126/90699677-c8722500-e27b-11ea-8c7e-a5a0d4a08429.png)
 
 ### En nvieau de gris:
 `Binaire: L'intensité prend la valeur 0 ou 1 (0 pour le noir, et 1 pour le Blanc) `
 
### En Couleur:

`RGB: prend 3 valeurs (intensités) : l'intensité du rouge, l'intensité du vert, l'intensité du bleu. et chaque intensité ne dépasse pas 255.`

![Histogramme](https://user-images.githubusercontent.com/38400126/90700029-a7f69a80-e27c-11ea-927e-78bee6b0d5d1.png)

`L'histogramme:` ce sont des bases sur le traitement d'image avant d'étudier les opérations 
donc c'est quoi l'hitogramme?
`c'est calcul de la somme et déssiner l'histogramme ( par ex: la somme des pixels horizontallement)`

`Un histogramme est un graphique statistique permettant de représenter la distribution des intensités des pixels d'une image, c'est-à-dire le nombre de pixels pour chaque intensité lumineuse. Par convention un histogramme représente le niveau d'intensité en abscisse en allant du plus foncé (à gauche) au plus clair (à droite).`

![normal](https://user-images.githubusercontent.com/38400126/90700266-3ec35700-e27d-11ea-816d-8d120f187fe6.png)

 C'est quoi `la normalisation d'histogramme?`
 
 C'est de transfomrer cette image en cette image pour bien visualiser l'image.
 on la calcule par cette formule: l'intensité du l'image résultat = l'intensité de l'image précédente originale....
 
 `la normalisation est un processus qui modifie la plage des valeurs d'intensité des pixels`
 
 ![égalisation](https://user-images.githubusercontent.com/38400126/90700446-cc9f4200-e27d-11ea-83e0-b559967e1626.png)
 
 `L'égalisation réalise une correction automatique de l'échelle des niveaux de gris de l'image, en fonction de son histogramme.`
 
 `l'égalisation d'histogramme est une méthode d'ajustement du contraste d'une image numérique qui utilise l'histogramme. Elle consiste à appliquer une transformation sur chaque pixel de l'image, et donc d'obtenir une nouvelle image à partir d'une opération indépendante sur chacun des pixels.`

![seuiillage](https://user-images.githubusercontent.com/38400126/90700517-f9535980-e27d-11ea-973b-912170807ad3.png)

`Le seuillage` c'est une opération très utilisée dans le traitement d'image il permet de transformer l'image en des `images binaires`. comme vous voyez ici cette image est en niveau gris et cette image est en binaire.
 `le principe en général c'est de prendre un seuil ajustatif de cette image, puis on va parcourir tous les pixels, si le pixel est inférieur au seuil, il prend la valeur 0, s'il est supérieur, il prend la valeur 1.`
 
 ### TP Egalisation:
 `Image Originale`
 
 ![imageORiginale](https://user-images.githubusercontent.com/38400126/90700950-0d4b8b00-e27f-11ea-98b2-99cdb6be2e1b.png)

` Résultat:`

![r](https://user-images.githubusercontent.com/38400126/90700972-1ccad400-e27f-11ea-8a5e-f49a04e62293.png)

### TP Histogramme Normalisation:
 `Image Originale`
 
 ![org](https://user-images.githubusercontent.com/38400126/90701210-c5793380-e27f-11ea-8afe-0b29ce6b5bc7.png)

`Résultat:`

![obtient](https://user-images.githubusercontent.com/38400126/90701212-c6aa6080-e27f-11ea-9d2f-d8f13981b883.png)

Si on applique `la normalisation+l'hitogramme de normalisation `bien sur, il nous donne des bons résultats.

`Résultat:`

![result](https://user-images.githubusercontent.com/38400126/90701323-096c3880-e280-11ea-9f48-621d44c1f22d.png)


## Détection des contours

### Introduction:

-Pour détecter `un objet` dans une scène la recherche de caractéristiques dans une image est nécessaire.
- Plusieurs types de caractérisqtiques: Contours, squellete, région.
- La détection des contours permet de garder que les informations significatives.
D'abord c'est quoi `le contour`?
`le contour` c'est détecter les objets dans une image. `par exemple dans cette image il ya une fille donc il faut détecter cette fille (Pour séparer l'objet avec l'arrière plan) `

### Applications:

 - Reconnaissance des formes, d'objets...
 - Classification des scènes
 - Compression
 
 ![contour](https://user-images.githubusercontent.com/38400126/90703452-b72e1600-e285-11ea-8e3e-dfa116999e6a.png)
 
 #### il existe plusieurs méthodes de détection de contour,
` - Deux approches sont les plus utilisées:`
 *Approximation du Gradient
 *Approximation du Laplacien

### le gradient d'une image

c'est ce qui est souvent utilisé pour `détecter des contours` dans une image. Le principe est de calculer la `dérivée du signal` dans `les directions horizontales et verticales`, puis de calculer `la norme du vecteur` formé par ces deux valeurs. Une manière assez directe et pratique est d'utiliser `le filtre de Sobel.`

![gradient](https://user-images.githubusercontent.com/38400126/90759447-5845bc80-e2d8-11ea-9256-de07dd2c13cd.png)

Puis on calcule `la dérivée par rapport x et y`, puis on calcule `le module` et on choisit `un seuil`. Si le `module < seuil` il prend la valeur `0` sinon `1` pour obtenir un contour c'est `une image noir et blanc`.

![op](https://user-images.githubusercontent.com/38400126/90760375-b030f300-e2d9-11ea-85a5-af214c86db99.png)


![opee](https://user-images.githubusercontent.com/38400126/90760660-22093c80-e2da-11ea-9222-6deceb94cab7.png)

![masque](https://user-images.githubusercontent.com/38400126/90760764-436a2880-e2da-11ea-83b2-0286395f5622.png)

![op1](https://user-images.githubusercontent.com/38400126/90760941-8a581e00-e2da-11ea-9953-6f080244518f.png)

![op2](https://user-images.githubusercontent.com/38400126/90761438-50d3e280-e2db-11ea-8f2e-46be1852c13a.png)

![op3](https://user-images.githubusercontent.com/38400126/90761447-53363c80-e2db-11ea-9567-7971cb2455ea.png)

`Et c'est ça le résultat qu'on a obtenu, on applique sur cette image ce masque et on obtient le contour vertical , et si on applique l'autre masque sur la même image on obtient le contour horizontal et on calcule le module obtenu (le module c'est l'image avec contour)`

il y a `d'autres masques` comme `le masque de Robert` qui contient 4 éléments:

![opRobert](https://user-images.githubusercontent.com/38400126/90762389-df952f00-e2dc-11ea-92f7-62fb844de675.png)

![Result](https://user-images.githubusercontent.com/38400126/90762393-e2901f80-e2dc-11ea-9119-123d019f9d8c.png)

![gradERR](https://user-images.githubusercontent.com/38400126/90762395-e459e300-e2dc-11ea-8263-4c163b5d8e2a.png)

### TP Gradient:

`Image initiale:`

![imageInit](https://user-images.githubusercontent.com/38400126/90762983-d6589200-e2dd-11ea-9f27-0fb5fe36759f.png)

`Résultat:`

![result](https://user-images.githubusercontent.com/38400126/90763001-da84af80-e2dd-11ea-99d4-1e5ea63552b9.png)

### Seuillage:

- Le seuillage fixe
- Le seuillage global
- Le seuillage local

![seuillage](https://user-images.githubusercontent.com/38400126/90765669-41a46300-e2e2-11ea-8804-42d4cf8f2adb.png)

![SeuillageFixe](https://user-images.githubusercontent.com/38400126/90765674-4537ea00-e2e2-11ea-8a49-05450dde50bf.png)

![seuillageGlobal](https://user-images.githubusercontent.com/38400126/90765680-4701ad80-e2e2-11ea-98ee-cf292a246963.png)

![seuillageLocal](https://user-images.githubusercontent.com/38400126/90765687-49640780-e2e2-11ea-867d-2f8cffa7d8b2.png)

![local1](https://user-images.githubusercontent.com/38400126/90765691-4a953480-e2e2-11ea-8d6d-ebf0cb8155aa.png)

On applique `le gradient` sur cette image et on obtient:

![imgIniti](https://user-images.githubusercontent.com/38400126/90765694-4c5ef800-e2e2-11ea-949d-e5562b0e4377.png)

`Résultat:`

![Resut](https://user-images.githubusercontent.com/38400126/90765703-4e28bb80-e2e2-11ea-9941-7552aa4b6baa.png)

On va appliquer `le seuillage fixe` avec un `seuil 20` sur l'image du `gradient` et on obtient:

`Résultat:`

![result](https://user-images.githubusercontent.com/38400126/90766122-f5a5ee00-e2e2-11ea-932b-d11dc79c6f91.png)

`Le gradient` nous donne pas plusieurs informations sur l'image.

Pour le résultat de `seuillage global`, on va appliquer `le seuillage global` sur `l'image du gradient`, et on obtient:

![yes](https://user-images.githubusercontent.com/38400126/90766536-9ac0c680-e2e3-11ea-9a0b-733fe99d2242.png)


Donc `le seuillage global` donne plusieurs informations que l`e seuillage fixe` et `le gradient`.



# QCM 

![Q1](https://user-images.githubusercontent.com/38400126/90625380-65e43f00-e211-11ea-8158-7162b23b6693.png) ![Q-1](https://user-images.githubusercontent.com/38400126/90625538-a6dc5380-e211-11ea-9b61-21694547a1c8.png)

![vrai](https://user-images.githubusercontent.com/38400126/90767324-eaec5880-e2e4-11ea-9a68-06a236b59908.png)

`RGB: prend 3 valeurs (intensités) : l'intensité du rouge, l'intensité du vert, l'intensité du bleu. et chaque intensité ne dépasse pas 255.`
`RGB = (8bits, 8bits, 8bits)`.


![Q6](https://user-images.githubusercontent.com/38400126/90770491-c5ae1900-e2e9-11ea-94e5-f77baa8969e1.png)

![Q7](https://user-images.githubusercontent.com/38400126/90771655-8680c780-e2eb-11ea-8165-d7dce75b056c.png)

On réalise `une synthèse additive` lorsque l'on `superpose plusieurs faisceaux de lumières colorées`.
`La synthèse additive` utilise généralement trois lumières colorées : `une rouge, une verte et une bleue (RVB ou RGB en anglais pour Red, Green, Blue)`. L'addition de ces trois lumières colorées en proportions convenables donne la lumière blanche. L'absence de lumière donne du noir.

Un vidéo projecteur projette l'image de trois rectangles de couleur R, V et B sur trois miroirs qui permettent de projeter ces trois couleurs au même endroit sur un écran.
En réglant la luminosité des trois couleurs, on réalise la synthèse additive de nombreuses couleurs.

![Q10](https://user-images.githubusercontent.com/38400126/90773394-ba5cec80-e2ed-11ea-94e3-f563fc2c0258.png)
![Q](https://user-images.githubusercontent.com/38400126/90773699-36573480-e2ee-11ea-857e-8b930906cf60.png)

![QQ](https://user-images.githubusercontent.com/38400126/90773801-61da1f00-e2ee-11ea-96af-d9f102372951.png)
![PBM](https://user-images.githubusercontent.com/38400126/90774371-4ae7fc80-e2ef-11ea-87f4-cd8c95b38d4a.png)
![exemples](https://user-images.githubusercontent.com/38400126/90774376-4d4a5680-e2ef-11ea-8627-4efe8c26e909.png)

![Q12](https://user-images.githubusercontent.com/38400126/90774977-2ccecc00-e2f0-11ea-8647-96e70f60da34.png)

![filtreSpatioal](https://user-images.githubusercontent.com/38400126/90776519-1a559200-e2f2-11ea-897c-398e3144777c.png)
![filtrage2](https://user-images.githubusercontent.com/38400126/90776523-1c1f5580-e2f2-11ea-9d54-dc75296196aa.png)

![Q15](https://user-images.githubusercontent.com/38400126/90777316-27bf4c00-e2f3-11ea-90a0-dfa830c7ccad.png)

#### numérisation de l’image
`filtre de reconstruction idéal`
Pour `ré-échantillonner` une image numérique, il faut construire implicitement sa `version analogique` :
`Le spectre du signal échantillonné est une répétition infinie du spectre de I(x , y ). Pour reconstruire ce dernier, il suffit d’appliquer à I e (x , y ) un filtre spatial passe-bas et appliquer ensuite la transformé de Fourier inverse pour récupérer I(x , y ).`

![1](https://user-images.githubusercontent.com/38400126/90777763-c51a8000-e2f3-11ea-9b91-caefde38d5db.png)
![2](https://user-images.githubusercontent.com/38400126/90777768-c5b31680-e2f3-11ea-9341-b0f0699e9af6.png)

![Q16](https://user-images.githubusercontent.com/38400126/90789177-80e0ad00-e2fe-11ea-90a6-f6a558bdf860.png)
![Q17](https://user-images.githubusercontent.com/38400126/90789176-80e0ad00-e2fe-11ea-93f0-aaf00007c86d.png)

Espace des fréquences spatiales :
À l’instar des signaux temporels, on définit la transformée de Fourier spatiale d’une image 2D par.

La notion de transformée de Fourier à deux dimensions est une généralisation de celle à une dimension.

`Soit f(x,y) une fonction à deux variables représentant l'intensité d'une image au point d'abscisse x et d'ordonnée y. La transformée de Fourier de cette image permet de passer d'une représentation spatiale à la représentation de l’image dans le domaine fréquentiel. Elle est donnée par :`

![18](https://user-images.githubusercontent.com/38400126/90792849-e9ca2400-e302-11ea-820a-3df77b796c79.png)

![19](https://user-images.githubusercontent.com/38400126/90793118-3dd50880-e303-11ea-82cb-c679eda97cf9.png)

![20](https://user-images.githubusercontent.com/38400126/90793119-3e6d9f00-e303-11ea-94b1-df5b555b78c9.png)

![21](https://user-images.githubusercontent.com/38400126/90795354-dc626900-e305-11ea-9010-9d3806930083.png)

![22](https://user-images.githubusercontent.com/38400126/90795445-f8fea100-e305-11ea-8f7e-643a58888eea.png)








### Github

`$ git init`

`$ git add -A`

`$ git commit -m "Add All Files"`

`$ git remote add github "Repository URL"`

`$ git push -f github master`



