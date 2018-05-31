# 2018_template_procedureCr_ipno
Version 1, portage LaTeX par Antoine Luboz (luboz@ipno.in2p3.fr).\n
Mise en page inspirée des documents PV et procédure d'Attrium.
## Présentation
Template LaTeX pour les comptes rendus, procédures et procès-verbaux.
Permet la rédaction de comptes-rendus, rapports techniques, procès-verbaux, etc. en utilisant la mise en page caractéristique et propre des documents rédigés en LaTeX.
Un très bon cours sur les bases du LaTeX est disponible sur Open Classrooms  https://openclassrooms.com/courses/redigez-des-documents-de-qualite-avec-latex
De plus, LaTeX dispose d'une communauté très active et la plupart des problèmes ou questions trouve une réponse très rapide avec une simple recherche Google.

Voici ci après quelques recommandations pour que la compilation du document se passe au mieux.

## Structure du projet
### Fichier projet LaTeX, dossier Files
Les fichiers nécessaires à la bonne compilation du projet sont situés dans le dossier files. Il est normalement pas nécessaire d'y toucher mais à titre informatif ou au vu de futures modifications. Chacun est libre de modifier la structure du projet, merci de maintenir le changelog à jour ainsi que le readme explicatif. Voici le détail du dossier:
#### Logos
les logos des instituts sont placés dans le dossier Logos - Merci de me contacter si vous trouvez un logo vectoriel de l'IPNO (format eps, svg, pdf).
#### changelog
répertorie les changements apportés à la structure des fichiers du projet. Tout changement est à signaler dans le fichier changelog.
#### commandes.tex
répertorie les commandes utilisables (guillemets français, nombres romains...) Dans la suite du document.
#### main.tex
est le fichier compilé, les autres fichiers tex sont inclus dans celui-ci.
#### packages.tex
contient la liste d'appels de packages et leurs options. C'est ici qu'on peut également modifier les options du langage informatique (citation de code avec lstlistings), l'affichage des nombres et unités (siunitx) ou la langue du texte.
#### titlepage.tex
est la page de garde.
#### unsrt-fr.bst
est le fichier de configuration pour une bibliographie s'affichant en français.
    
### Fichiers à modifier
Les seuls fichiers qui nécessitent une modification sont normalement ceux listés à la racine. Chacun contiennent des instructions en en-tête en commentaire LaTeX (```%```). Voici une liste avec description succincte.
#### configuration.tex
Fichier de configuration du document où on indique l'auteur, le titre...
#### histModifications.tex
Tableau dans lequel on indique l'historique des modifications de la lignée de fichier, rajoutez une ligne par nouveau fichier diffusé.
#### resume.tex
Résumé du fichier que l'on crée qui s'affichera sur la page de garde, restez succins.
#### bibliographie.bib
Fichier répertoriant les références bibliographiques au format BibTeX.
#### contenu.tex
Le contenu à proprement parler du document, on utilise les balises ```\chapter{}```, ```\section{}``` et autres commandes LaTeX.
##### annexes.tex
Contient les annexes, écrivez en utilisant la même structure que pour le corps. La numérotation sera effectuée automatiquement et différemment des sections précédent l'annexe.
##### Dossier figures ou fichiersAnnexes
N'hesitez pas à placer les figures et fichiers annexes (code par exemple) dans un dossier à la racine. Les figures seront alors appelées par
```{tex}
\includegraphics[scale = <0 à 1>, width = <##cm>, height = <##cm>]{Dossier/nomDuGraphique.extension}
```
##### glossaire.tex
Permet la création d'un glossaire. Consultez l'aide du package glossaries. (ne marche pour le moment pas)

## Recommandations, conseils et instructions
### Conseils d'ordre général
Compiler sur le fichier ```files/main.tex```

Utilisez `\frquotes{}` pour les guillemets français
Dans la page de configuration, remplacez les accents comme suit:
        é devient ```\'{e}```
        à devient ```\`{a}```
        Ë devient ```\"{E}```

Utilisez la recherche et remplacement CTRL + F, _cf._ documentation pour d'autres types d'accents.

### Bibliographie
La plupart des références bibliographiques peuvent-être trouvées sur Google Scholar, Mendeley... en choisissant d'exporter en BIB.
 Une référence se présente sous cette forme:
        ```@type{tag, title = {titre}, author = {auteur}, year = {année}, month = mois {jan,feb...}, <d'autres paramètres spécifiques aux différents types>}```
        Une référence est citée en utilisant la commande ```\cite{tag}```, les références peuvent-être combinées ```\cite{tag1,tag2}```.
