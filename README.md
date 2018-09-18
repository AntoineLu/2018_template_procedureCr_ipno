# 2018_template_procedureCr_ipno - Readme
Version 2, portage LaTeX par Antoine Luboz (luboz@ipno.in2p3.fr). Mise en page inspirée des documents PV et procédure d'Attrium (Véronique Poux).

## Description
Template LaTeX pour les comptes rendus, procédures et procès-verbaux.
Permet la rédaction de comptes-rendus, rapports techniques, procès-verbaux, etc. en utilisant la mise en page caractéristique et propre des documents rédigés en LaTeX.

## Recommandations, conseils et instructions
### Cours LaTeX en ligne
Voici ci après quelques recommandations pour que la compilation du document se passe au mieux.  
On conseillera l'utilisation du service en ligne [Overleaf V2](https://www.sharelatex.com?r=769c675e&rm=d&rs=b) permettant d'oublier les tracas liés à l'installation des _packages_. Pour une utilisation de LaTeX local sous Windows, préférez la distribution [MikTeX](https://miktex.org/download) avec un éditeur comme texmaker, texlive ou directement [notepad++](https://notepad-plus-plus.org/download/v7.5.6.html) pour les plus aguéris. Sous Linux, la distribution TeX Live semble être la plus utilisée.
De très bon cours sur les bases du LaTeX sont disponible [sur Open Classrooms](https://openclassrooms.com/courses/redigez-des-documents-de-qualite-avec-latex) ou directement [sur ShareLaTeX](https://fr.sharelatex.com/learn/).
De plus, LaTeX dispose d'une communauté très active et la plupart des problèmes ou questions trouve une réponse très rapide avec une simple recherche Google!

### Conseils d'ordre général, résumé succin du fonctionnement de LaTeX
Compiler sur le fichier ```Files/main.tex``` avec pdfLaTeX.  
S'il y a un problème d'accentuation, remplacez les lettres accentuées comme suit: `é` devient ```\'{e}```, `à` devient ```\`{a}```, `Ë` devient ```\"{E}```...  
Utilisez la recherche et remplacement CTRL + F, _cf._ documentation pour d'autres types d'accents.  
Il est conseillé d'utiliser des images vectorielles (PDF) pour une meilleur qualité du document final.
Voir la [section suivante](#commandes-supplémentaires) pour les commandes supplémentaires ajoutée.

### Propriété de l'emphase
La commande `\emph{<texte>}` permet de mettre en valeur un élément de texte en s'adaptant à l'environnement (paragraphe) dans lequel le texte se situe. Par exemple, si le paragraphe est droit, la commande mettra le texte séléctionné en italique. Si le paragraphe est italique, alors la commande tournera la selection en texte droit. Si le paragraphe est gras, alors le texte selectionné sera droit et clair et ainsi de suite. Il est possible de changer le formattage par défaut (voir sur Internet) ou de forcer un format particulier avec les commandes suivantes: `\textbf{<texte à afficher en gras>}`, `\textit{<texte à afficher en italique>}`, `\texttt{<texte à afficher en largeur fixe « machine à écrire »>}`, `\uline{<texte à souligner>}`, `\sout{<texte à barrer>}`
\xout{Texte à hachurer}, et `\uwave{<texte à souligner par une vaguelette>}`  (`\text{<texte droit en mode math>}`).

### Bibliographie
La plupart des références bibliographiques peuvent-être trouvées sur Google Scholar, Mendeley... en choisissant d'exporter en BIB.  
Une référence se présente sous cette forme:
- ```@type{<tag>, title = {<titre>}, author = {<auteur>}, year = <année>, month = <mois, érire directement jan,feb...>, <d'autres paramètres spécifiques aux différents types>}```. Cette entrée sera écrite dans le fichier `bibliographie.bib`.
- Une référence du fichier est citée en utilisant la commande `\cite{<tag>}` dans le texte. Les références peuvent-être combinées `\cite{<tag1>,<tag2>}`.

### Commandes supplémentaires
Voici la liste des quelques commandes supplémentaires au LaTeX « de base » et leur description :
- `\frquotes{<texte>}` permet d'afficher des guillemets français.
- `\enquote{<texte>}` permet d'afficher des guillemets anglais simples.
- `\enquotes{<texte>}` permet d'afficher des guillemets anglais doubles.
- `\dequotes{<texte>}` permet d'afficher des guillemets allemands.
- `\RNum{<nombre>}` permet d'afficher un nombre en chiffre romain.
- `\abs{<texte ou nombre>}` permet d'afficher un caractère entre les barres de valeur absolue, à utiliser en mode math.
- `\norme{<texte>}` permet d'afficher la norme d'un vecteur (doubles barres), à utiliser en mode math.
- environnement commentaire `\begin{commentaire}{<auteur du commentaire>}<texte>\end{commentaire}` permet d'afficher le commentaire à un paragraphe du texte. Si le commentaire se retrouve sur une page séparée du paragraphe qu'il est censé commenter, placez le commentaire et son paragraphe lié dans un environnement `samepage`: `\begin{samepage}<paragraphe et commentaire>\end{samepage}`.

## Structure du projet
### Fichiers à modifier
Les seuls fichiers qui nécessitent une modification sont en face avant (listés directement à la racine). Chacun contiennent des instructions en en-tête en commentaire LaTeX (`%`). Voici une liste avec description succincte.
#### configuration.sty
Fichier de configuration du document où on indique l'auteur, le titre, l'utilisation ou non de bibliographies...
#### histModifications.tex
Tableau dans lequel on indique l'historique des modifications de la lignée de fichier, rajoutez une ligne par nouveau fichier diffusé.
#### resume.tex
Résumé du fichier que l'on crée qui s'affichera sur la page de garde, restez succins.
#### contenu.tex
Le contenu à proprement parler du document, on utilise les balises `\chapter{<titre du chapitre>}`, `\section{<titre de la section>}` et autres commandes LaTeX.
#### bibliographie.bib
Fichier répertoriant les références bibliographiques au format BibTeX.
##### annexes.tex
Contient les annexes, écrivez en utilisant la même structure que pour le corps. La numérotation sera effectuée automatiquement et différemment des sections précédent l'annexe.
##### Dossier figures ou fichiersAnnexes
N'hesitez pas à placer les figures et fichiers annexes (extraits de code par exemple) dans un dossier à la racine. Les figures seront alors appelées par
```{tex}
\includegraphics[scale = <0 à 1> ou width = <##cm>, height = <##cm>]{<chemin vers le fichier>/<nom du graphique>.<extension>}
```
##### glossaire.tex
Permet la création d'un glossaire. Consultez l'aide du package glossaries. (ne marche pour le moment pas)

### Fichier projet LaTeX, dossier Files
Les fichiers nécessaires à la bonne compilation du projet sont situés dans le dossier files. Il est normalement pas nécessaire d'y toucher mais à titre informatif ou au vu de futures modifications. Chacun est libre de modifier la structure du projet, merci de maintenir le changelog à jour ainsi que le readme explicatif. Voici le détail du dossier:
#### Logos
les logos des instituts sont placés dans le dossier Logos - Merci de me contacter si vous trouvez un logo vectoriel de l'IPNO (format eps, svg, pdf).
#### changelog
répertorie les changements apportés à la structure des fichiers du projet. Tout changement est à signaler dans le fichier changelog.
#### commandes.tex
répertorie les commandes utilisables (guillemets français, nombres romains...) Dans la suite du document.
#### main.tex
est le fichier à compiler avec pdfLaTeX, les autres fichiers tex sont inclus dans celui-ci.
#### packages.tex
contient la liste d'appels de packages et leurs options. C'est ici qu'on peut également modifier les options du langage informatique (citation de code avec lstlistings), l'affichage des nombres et unités (siunitx) ou la langue du texte.
#### titlepage.tex
est la page de garde.
#### unsrt-fr.bst
est le fichier de configuration pour une bibliographie s'affichant en français.
