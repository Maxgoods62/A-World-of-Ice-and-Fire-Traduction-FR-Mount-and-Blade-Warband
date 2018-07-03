# Traduction française du mod A World of Ice and Fire du jeu Mount and Blade Warband

**Une nouvelle traduction est en cours de developpement, l'ancienne traduction est disponible dans la branche "v1.3"**

La traduction vient de commencer ! J'estime que j'ai traduit 15% des fichiers. [03/07/2018]

Version du mod traduit : v3.6

Lien du mod : http://www.moddb.com/mods/a-world-of-ice-and-fire

## Installation

Pour installer la traduction, il faut que vous telechargiez ces fichiers puis allez dans le répertoire du mod puis dans le dossier "languages" et mettez le dossier "fr" dedans.

## Remarques

Il est extrêmement probable qu'il exite des fautes de frappe, de conjugaison, de texte non traduit etc.

Vous pouvez m'aider en répertoriant ces anomalies en créant une nouvelle issue à ce projet github.

## Astuce pour les traducteurs (niveau avancé)

J’en profite pour donner une petite astuce à ceux qui traduisent des mods de Mount And Blade. En ce qui concerne le fichier troops.csv, il est assez chiant et répétitif de traduire de l’Anglais au Français. En effet, dans la plupart des cas, les adjectifs en français se trouvent après le nom alors qu’en anglais, c’est l’inverse.


Par exemple “Nord Spearman” en anglais devient “Nord Lancier” en français si on traduit automatiquement tous les “Spearman” en “Lancier”. On remplace alors “Nord” par “du Nord” pour que ça soit un peu plus français. Jusqu'ici, c’est automatique. 

Enfin, on doit donc passer à la main pour mettre “du Nord” après “Lancier” pour CHAQUE LIGNE de ce type.


Et bien avec Notepad++, j’ai fait une regex qui permet au-to-ma-ti-que-ment de le faire :) Ça économise pas mal de temps

### Mode d'emploi
- Sélectionnez la portion de texte auquel il faut activer la modification, faites CTRL+H (remplacer)
- Dans Mode de recherche, cocher “Expression Régulière”
- Dans Rechercher, mettez : `([^|]*)([\|])([^\s]*)([^\S]*)([^{***}]*)`
- Dans Replacer par, mettez : `\1\2\5 \3`
- Cocher “Dans la sélection” et “Respecter la case”
- Cliquez sur Remplacer tout et magie !


Voici une ligne type de ce à quoi ça doit ressembler pour fonctionner :
`trp_stormlands_local_lord_pl|Stormlands Seigneurs{***}` 
(il faut qu’il y ait **`{***}`** à la fin de la ligne pour que ça fonctionne !)

Ça fonctionne aussi pour les noms-composés
`trp_stormlands_messenger|Stormlands Messenger testa testb testc{***}` devient `trp_stormlands_messenger|Messenger testa testb testc Stormlands{***}`


Si vous voulez que ça enlève `{***}` en même temps, ajoutez ça à la fin de la regex(Recherche) :   `(.*)`


La regex n’est pas optimale je pense mais ça fonctionne ^^ J’espère que ça peut être utile à d’autres gens.

