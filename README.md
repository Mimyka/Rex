Rex
===

Plus qu'un simple framework, un ami pour la vie.

Installation
------------

Vous pouvez directement télécharger le projet [ici][] ou en utilisant cette commande.

```shell
$ git clone https://github.com/Mimyka/Rex.git
```

Et vous pouvez aussi utiliser ce CDN:

``` html
<link rel="stylesheet" href="https://cdn.rawgit.com/Mimyka/Rex/0.1.2/rex.min.css">
```

[ici]: https://github.com/Mimyka/Rex/blob/master/rex.min.css

Caractéristiques
----------------

Rex est un framework CSS sur la base de flexbox.
Il a été conçu pour être léger et coder beaucoup plus rapidement.

* Une grille responsive adaptable en fonction de vos besoins (SASS).

* Pas de style interne, ce qui vous laisse designer librement vos projets.

* Une syntaxe rapide et minimaliste

* Mobile first

* Un poids léger (18.9ko minifié)

* Utilisant la technologie moderne qu'est le Flexbox

* Simple à utiliser et à apprendre

Fichiers
--------

* `/rex.min.css`: Le framework, minifié, avec préfixes vendeurs, destiné à la production.

Les fichiers dans le dossier src (source) sont destinés au développement.

* `/src/css/rex.css`: Le framework tout juste compilé, sans prefixes vendeurs.

* `/src/sass/rex.sass`: Base de développement, importations d'autres fichiers sass.

* `/src/sass/var.sass`: Peut être utilisé pour personnaliser le nombre de colonnes, les breakpoints, les préfixes responsive.

* `/src/sass/_*.sass`: Tout les fichiers importés dans rex.sass, entre autres le système de grid.

Documentation
-------------

Rex fonctionne avec un système de lignes et de colonnes flex.
* `.r` : ligne (row)
* `.c` : colonne (column)

``` css
/* Pour le nowrap, il y a aussi les classes .r-no et .c-no */
.r{
    display: flex;
    flex-wrap: wrap;
}
.c{
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
}
```

On utilise dans celles ci, des unités allant de 1 à 24.
* `.u-[nbr]` : unité (unit)

``` css
/* Il y a aussi la classe .u qui correspond à flex: 1 */
.u-24{
    width: 100%;
}
.u-23{
    width: 95.83333%;     
}
.u-22{
    ...
}
```

Pour placer ces unit, on peut utiliser toutes les propriétés d'align-items/content/self et justify-content:
* `.[x|y]-start` : alignement sur l'axe au début (défaut)
* `.[x|y]-end` : alignement sur l'axe à la fin
* `.[x|y]-center` : alignement sur l'axe au centre
* `.[x|y]-around` : alignement sur l'axe en mode space-around
* `.[x|y]-between` : alignement sur l'axe en mode space-between
* `.start` : alignement de l'élément choisi en mode align-self: start
* `.end` : alignement de l'élément choisi en mode align-self: end
* `.center` : alignement de l'élément choisi en mode align-self: center

Ces propriétés doivent être appliqué sur une ligne ou une colonne flex pour ainsi aligner les éléments enfants :

``` html
<div class="r x-center y-center">
    <div>
	<!-- Centré horizontalement ainsi que verticalement par rapport à mon parent -->
    </div>
    <div class="end">
	<!-- Centré horizontalement et verticalement à la fin de mon parent -->
    </div>
</div>
<!-- Tips: On peut utiliser ces propriétés sans se soucier de l'inversement des axes en mode colonne, rex est là pour ça ;) -->
```

Également disponible, un système d'offset également basé de 1 à 24:
* `.o-[nbr]` : offset

``` css
.o-24{
    margin-left: 100%;
}
.o-23{
    margin-left: 95.83333%;     
}
.o-22{
    ...
}
```

Aussi présente la classe hidden.
* `.hidden` : hidden

``` css
.hidden{
    display: none;
}
```


A tout ceci, l'on peut ajouter librement des préfixes pour faire du responsive. (sauf pour les row et column)
* `...` : all
* `.s-...` : >= 568px
* `.m-...` : >= 768px
* `.l-...` : >= 1080px
* `.xl-...` : >= 1280px


Compatibilité navigateurs
-------------------------

Les tests n'ont pas encore été tous accomplis.
Rex fonctionne normalement sous :

* IE 10+
* Latest Stable: Firefox, Chrome, Safari, Opéra
* Android 4.2+ (partial support Android 2.1+, wrapping not supported)

Si vous rencontrez des bugs sous ces versions, n'hésitez pas à nous en faire part.

Pour assurer une plus grande compatibilité, vous pouvez utiliser [Flexibility.js][].

[Flexibility.js]: https://github.com/jonathantneal/flexibility

Licence
-------

Rex est sous licence MIT.
Regardez le [fichier de LICENCE][] pour plus d'informations.


[fichier de LICENCE]: https://github.com/Mimyka/Rex/blob/master/LICENSE
