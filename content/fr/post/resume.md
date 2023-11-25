---
date: 2023-11-18T00:00:00-04:00
description: "Résumé du cours"
featured_image: "/images/hugo-logo-wide.svg"
title: "Résumé du cours"
---


# Résumé du cours - Hugo / Github

## Introduction
Nous avons réalisé la mise en place d'un projet basé sur ***Hugo*** en y découvrant les bases et par la suite approfondie ces dernières lors de l'exploration des différents moyens de personnaliser un thème déjà existant. Le déploiement et l'automatisation avec ***Github Pages*** furent aussi des points abordés durant cette phase de découverte.

 1. ## Remise à plat des fondamentaux de Git et GitHub
Après avoir réintroduit les principes de base et la *distinction* entre ***Git*** et ***GitHub***, nous avons construit un site Hugo en reprenant le thème "Ananke" avant de le déployer sur nos comptes GtiHub personnels pour configurer dans un premier ***Github Pages*** puis ***Github Action*** par le biais d'un fichier ***hugo.yml*** (il s'agit d'un fichier de configuration au même titre que `.gitlab-ci.yml`)

2. ## Construction de Sites avec Hugo
Pour commencer, il fallait installer au préalable Hugo sur sa machine, en faisant attention à sélectionner la version “extended” afin d’avoir accès à tous les fonctionnalités, puis se crée un projet Hugo ainsi que quelques pages de contenu afin de toucher un peu au fonctionnement de celui-ci.

Il est plus simple de procéder aux modifications en utilisant le serveur live proposé avec la commande :
```
hugo server -D
```

3. ## Personnalisation et Thèmes Hugo
Ici commence tout l’enjeu des thèmes. Vous pouvez bien évidemment créer celui-ci de zéro ; mais la possibilité de se baser sur un déjà existant puis le modifier à votre guise vous est aussi proposée.

Comme cité plus haut, dans mon cas je me suis permis de continuer à travailler sur le thème "Ananke" proposer dans le tutoriel d'Hugo, que vous pouvez retrouver [ici](https://gohugo.io/getting-started/quick-start/) et avec une documentation plus approfondie sur ce [lien](https://themes.gohugo.io/themes/gohugo-theme-ananke/).

Afin de personnaliser un thème, il faut créé une copie des fichiers qu'il contient en dehors de son dossier, en s'assurant se recréent les fichiers et dossiers avec les mêmes noms et chemins.

Assurez-vous de continuer à utiliser les variables d'Hugo pour appeler les données dont vous aurez besoin comme `.Title` renvoyant la variable du titre de votre poste.
Avec la modification des fichiers html vient aussi la liberté d'ajouter du style ou des scripts avec un fichier *custom.css* (par défaut) et du javascript dans vos pages. Notez que Hugo possède aussi son propre langage et donc des conditions comme :

    {{ $featured_image := partial  "func/GetFeaturedImage.html" . }}

4. ## Création et gestions des contenus
Comme l'article que vous lisez actuellement, il s'agit d'un fichier ***Markdown*** que Hugo interprète et combiner aux templates correspondants, permet leur mise en page comme vous pouvez le constater.
Ces fichiers sont décomposés en deux parties :
- La première contenant toutes les informations que vous souhaitez lui attribuer (date, titre, image, taxonomie...)
- Et la deuxième se chargeant du contenu, de la disposition de vos médias...
![enter image description here](https://kinsta.com/wp-content/uploads/2021/09/pasted-image-0-3.jpg)

5. ## Le fichier "hugo.toml"
Il s'agit du fichier contenant les informations de votre site (URL, thème, langage...), mais aussi de la personnalisation de certaines variables utilisables dans l'ensemble du site.
Si vous souhaitez avoir plusieurs langages avec des configurations différentes :

```
[languages] 
	[languages.en] 
		title = "Spidercat🐱🕸️" 
		weight = 1 
		contentDir = "content/en" 
		# languageDirection = 'rtl' for Right-To-Left languages 
	[languages.fr] 
		title = "Spidercat🐱🕸️" 
		weight = 2 
		contentDir = "content/fr" 
```

Certains thèmes utiliseront ces variables, mais comme nous customisons ou créons le nôtre, libre à chacun de rajouter ce qui lui plaît ou lui semble utile (comme la couleur du texte par défaut sur notre site).

---

Pour faire un retour sur mon expérience d'Hugo, j'avais déjà eu l'occasion d'utiliser des générateurs de sites statiques (11ty) et j'ai pu y retrouver certains points communs. Mais j'ai regretté de constater que la documentation pour aller plus loin était peu présente. 

Beaucoup d'informations sont partagées entre utilisateurs sur des forums, mais certains principes de base ne figurent pas ou mal sur les sites dédiés (comme celui sur Ananké).
Le déploiement automatique est plutôt agréable et très simple à mettre en place, Github propose même une configuration ciblée Hugo quand on arrive sur celui-ci.
