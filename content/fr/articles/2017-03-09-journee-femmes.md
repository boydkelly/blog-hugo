---
title: 'Droit des femmes et traduction ?'
date: '2017-03-09'
type: 'post'
categories: ['Régionalisation']
tags: ['fedora-fr', 'traduction', 'planet-libre']
author: 'Jean-Baptiste Holcroft'
---

Quel rapport entre le logiciel libre et la journée du droit des femmes ? La qualité de la traduction et de l’internationalisation ! Ici on s’intéressera aux cas concrêts pour ouvrir son logiciel aux minorités, et les femmes sont trop peu présentes dans l’informatique.

En réalisant la mise à jour des applications [YunoHost](http://yunohost.org) sur mon serveur ce matin, l’interface me demande « Êtes-vous sur de vouloir mettre à jour de tous les applications ? ».

Ici, en plus du petit détail d’accent circonflexe manquant (sûr : être certain, sur : être dessus), on remarque donc deux problèmes liés au genre.

Si l’anglais permet très souvent l’usage de mots neutres, le français tend a donner un genre beaucoup plus rapidement. En anglais, effectivement cela ne se remarque pas : « Are you sure you want update every %s 1 ? ».

On découvre via la phrase source un problème de plus, ici le développeur utilise la même phrase pour parler de choses différentes « %s » peut être un paquet ou une application comme [on le voit dans le code du projet](https://github.com/YunoHost/yunohost-admin/blob/d1e17af0bb62549c462d99d5965ce9412c16b552/src/js/yunohost/controllers/tools.js#L77)… Eh bien ici on donc un problème de traduction et un problème d’internationalisation ! D’ailleurs [il y en a d’autres](https://github.com/YunoHost/yunohost-admin/blob/d1e17af0bb62549c462d99d5965ce9412c16b552/src/js/yunohost/controllers/tools.js#L70).

Pour le problème de traduction, le fait de sous-entendre que l’utilisateur est un homme peut être résolu très simplement avec la tournure « Voulez-vous vraiment ». Ce n’est pas plus complexe à comprendre et cela utilise moins de place dans les interfaces, tout en étant un peu plus accueillant et équitable.

Pour le second problème, écrire « toutes » rendra cette phrase juste quand on parle d’application, mais fausse quand on parle de paquet. D’ailleurs, rien ne permet d’affirmer que le mot Application ou Paquet sera à la même place dans la phrase pour toutes les langues.

Sur ce dernier point, deux éléments sont importants et intéressants, l’emplacement des mots dans la phrase et la grammaire.

Concernant l’emplacement des mots – la FSF donne un lien très intéressant concernant la traduction sur la page décrivant son [projet prioritaire d’internationalisation](https://www.fsf.org/campaigns/priority-projects/internationalization), c’est un article du [W3C y décrit les enjeux rudimentaires de l’internationalisation](https://www.w3.org/standards/webdesign/i18n) liés au positionnement des mots dans les phrases selon les langues. Pour aller plus loin, [tout ce site concernant l'internationalisation est très intéressant (et traduit)](https://www.w3.org/International/).

Concernant la grammaire, certaines langues changent d’orthographe de ses mots en fonction de leur rapport aux autres mots. C’est par exemple le cas des déclinaisons en allemand. Sceptiques ? Voici un exemple avec le site vitrine getfedora cette fois-ci en polonais. « Choisissez la liberté. Choisissez Fedora » est traduit « [Wybierz wolność. Wybierz Fedorę](https://getfedora.org/pl/). ». Wikimédia m’apprend aujourd’hui qu’il s’agit de « langues flexionnelles ». Donc le fait de dissocier l’objet de la phrase mène très probablement à une mauvaise traduction (le contexte manque et le temps pour fouiller dans le code afin de comprendre n'est souvent pas pris).

Et encore, je n’ai pas traité ici le fait que mettre à jour « une application » ou « plusieurs applications » devrait pouvoir être traduit différemment ! En français c’est simplement deux possibilités (singulier ou pluriel), mais dans d’autres langues, il y a plusieurs formulations possibles… Voir sur le sujet la [documentation Gettext](https://www.gnu.org/software/gettext/manual/html_node/Plural-forms.html) ou [Android](https://developer.android.com/guide/topics/resources/string-resource.html#Plurals).

Conclusion : internationaliser un logiciel et le traduit est une activité nécessitant beaucoup d’attention pour les développeurs, en plus de l’utilisation d’outils dédiés tel que gettext, il y a des règles de développement qu’il faut respecter, faute de quoi on pense bien faire, mais on ne couvre que de façon très imparfaite les cas effectivement rencontrés par les traducteurs.
