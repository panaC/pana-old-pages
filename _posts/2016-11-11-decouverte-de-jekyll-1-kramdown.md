---
layout: post
title: "découverte de jekyll : #1 Kramdown"
description: "présentation et syntaxe de Kramdown, Article de la série sur jekyll ruby. "
modified:
tags: [ jekyll, web, markdown ]

---

> Kramdown est cool

Je me lance dans le premier article de ce blog,
(je ne sais pas combien d'article je réaliserai);
Et je commence par une découverte de jekyll et de son environnement (fonctionnement, theme, plugins, etc).
Et une fois n'est pas coutume je démarre par un outil qui n'est pas propre à jekyll le Kramdown.
Tout simplement puisque je ne connais pas bien sa syntaxe. Fortement nécessaire pour écrire des articles sur ce blog.

Le [Kramdown](http://kramdown.gettalong.org/) est un langage de balisage pour la mise en forme de document html ou autres.

<div id="toc"></div>

Tout d'abord pourquoi le Kramdown et pas [l'asciiDoc](http://www.methods.co.nz/asciidoc/), le [pandoc](http://johnmacfarlane.net/pandoc/) ou tout simplement le [Markdown](https://fr.wikipedia.org/wiki/Markdown).

Le Kramdown est le langage par défaut sur jekyll et de plus il est plus complet que le markdown tout en restant aussi simple. Pour les autres langages de balisage, je ne les connais pas bien. Et quand l'envie m'en prendra de changer je ne manquerais pas de faire un comparatif des langages les plus connus.

![https://www.npmjs.com/package/markdown-live](http://i.giphy.com/lw3NLob8u3NrG.gif)

<em> [markdown-live](https://www.npmjs.com/package/markdown-live) </em>

# Le langage

Basé sur Ruby ( à partir de 1.8.7) 

[Github](https://github.com/gettalong/kramdown)

## Installation

Comme pour beaucoup de paquet Ruby, il est disponible chez l'hébergeur rubygems.

	gem install kramdown

# La Syntaxe

2 docs officiels sont disponibles :

* [Syntaxe exhaustive](http://kramdown.gettalong.org//syntax.html)
* [Syntaxe Essentiel](http://kramdown.gettalong.org/quickref.html)


## Elements texte

*Italics*

	*Italics*

**Gras**

	**Gras**

<u>Souligné</u>

	<u>Souligné</u>
	
__recopie__

	__recopie__

## Citation

> Citation

	> Citation

## Bloc de code

	Code source

~~~
	Code source
~~~


	Code source

~~~
---
Code Source
---
~~~

	Code source

~~~
	~~~
	Code Source
	~~~
~~~

```html
<a href="#" class="btn btn-success">Success Button</a>
```

~~~

```html
<a href="#" class="btn btn-success">Success Button</a>
```
~~~

## Séparateur

 * * *
 
	* * *
	
	 _  _  _  _
	 
	 ----------------

## Liste

1. liste 1
1. Liste 2
1. LISTE 3

~~~

	1. liste 1
	1. Liste 2
	1. LISTE 3
	
~~~
	
* une autre lise
* encore

~~~

	* une autre lise
	* encore
	
~~~


* une
+ liste
- différente

~~~

	* une
	+ liste
	- différente
	
~~~

## Définition

Kramdown
: Langage de balisage

Ruby
: Langage de script

~~~

	Kramdown
	: Langage de balisage

	Ruby
	: Langage de script
~~~

## Table

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3
{: rules="groups"}



	| Header1 | Header2 | Header3 |
	|:--------|:-------:|--------:|
	| cell1   | cell2   | cell3   |
	| cell4   | cell5   | cell6   |
	|----
	| cell1   | cell2   | cell3   |
	| cell4   | cell5   | cell6   |
	|=====
	| Foot1   | Foot2   | Foot3
	{: rules="groups"}

## Atribut html par balisage

> Une citation avec attribut
{: .classe style="color: blue"}

	> Une citation avec attribut
	{: .classe style="color: blue"}
	

## Lien

un [Lien](www.google.fr)

	un [Lien](http://www.google.fr)
	

un [second][lien]

texte ...

[lien]: http://www.google.fr

~~~

un [second][lien]

texte ...

[lien]: http://www.google.fr

~~~

## Image

une ![Image](https://cdn.pixabay.com/photo/2016/11/04/21/34/landscape-1799006_960_720.jpg)

	une ![Image](https://cdn.pixabay.com/photo/2016/11/04/21/34/landscape-1799006_960_720.jpg)
	
	
## Code intégré dans du texte

Pour avoir une toc : `<div id="toc"></div>` dans le fichier

	Pour avoir une toc : `<div id="toc"></div>` dans le fichier

## Note de bas de page

Un texte avec une note[^1].

[^1]: Une note de bas de page

~~~
Un texte avec une note[^1].

[^1]: Une note de bas de page
~~~

# Particularité

> Rien n'empeche de marier du Kramdown - Markdown - Html directement dans le ficher `.md`

Ceci est un <span style="color: red">texte rouge</span>. 

	Ceci est un <span style="color: red">texte rouge</span>. 

# Conclusion

Lors de la rédaction de ce poste j'ai pu remarquer beaucoup de petite subtilité dans le maniement de l'Html. 
La documentation exhaustive est agrémentée de pas mal d'exemples pour la compréhension.

Concernant la robustesse : je n'ai pas remarqué de souci de parser.
Ce qui est un vrai plus(+) car en cas de bug : 
il n'y a rien de plus chiant que de manipuler 
les balises et de bidouller pour que cela convienne.

L'ajout de balise Html directement dans le fichier `.md` permet de personnaliser à la volée si le Kramdown devient limité.
Ainsi par exemple j'ajoute un sommaire par `div` quand cela est nécessaire dans le poste.

---