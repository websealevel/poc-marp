# Marp

## Instalation du programme en ligne de commande (`marp-cli`)

Toutes les possibilités d'installation de l'application sont listées [sur le dépôt](https://github.com/marp-team/marp-cli).

### macOS

Installer marp via le gestionnaire de paquets [Homebrew](https://brew.sh/index_fr)

~~~bash
brew install marp-cli
~~~

### Windows

Installer marp via le gestionnaire de paquets [Scoop](https://scoop.sh/)

~~~bash
scoop install marp
~~~

### Debian/Ubuntu

#### Installation via les binaires

Télécharger l'archive contenant les binaires [depuis son dépôt GitHub](https://github.com/marp-team/marp-cli/releases).

Extraire l'archive

~~~bash
tar xvzf marp-cli-v{derniere version}-linux-tar.gz
~~~

Copiez l'éxecutable présent dans l'archive dans un répertoire présent sur le `PATH`, par exemple

~~~bash
sudo cp marp /usr/local/bin
~~~

Vérifier que marp est bien installé

~~~bash
marp -h
~~~

#### Installation via `node` et `npm`

Installer [node](https://packages.debian.org/fr/sid/nodejs) et [npm](le gestionnaire de paquets de node), puis installer `marp-cli` globalement (option `-g`)

~~~bash
sudo apt-get update
sudo apt-get install nodejs npm
npm install -g @marp-team/marp-cli
~~~

## Liste des options

Consulter la liste des options offertes par marp

~~~bash
marp -h
~~~

Il est possible de mettre toutes les options dans un fichier de configuration marp.conf, puis de le charger

~~~bash
marp -c marp.conf slide-deck.md
~~~

## Watch

On peut également observer notre fichier de présentation markdown avec l'option `-w`

~~~bash
marp -w slide-deck.md
~~~

Marp convertira uniquement le fichier indiqué lorsqu'il observera des modifications (ici en HTML par défaut). On peut donc ouvrir la présentation HTML générée dans notre navigateur pour avoir une preview optimisée avec un *hot reload*.

## Conversion

### au format PDF

Utilise Chrome ou Chromium

~~~bash
marp --pdf slide-deck.md
~~~

### au format HTML

~~~bash
marp slide-deck.md
~~~

### au format PPTX (powerpoint) **lecture seule**

La conversion opère juste une conversion en images au format `.pptx`. Le document peut être ouvert dans powerpoint mais **non éditable**

~~~bash
marp --pptx slide-deck.md
~~~

### au format PPTX (powerpoint) **éditable**

Pour convertir la présentation markdown en pptx éditable, on peut 

- passer [par le format PDF](#au-format-pdf) puis utiliser un outil comme [PDF to Powerpoint Converter](https://pdf.online/pdf-to-powerpoint-converter) ou [Adobe](https://www.adobe.com/acrobat/online/pdf-to-ppt.html)

## Conversion avec inclusion de fichiers multimédias

Il faut forcer le html avec l'option `--html`. Pour des exports PDF ou pptx, il faut également autoriser les fichiers locaux avec l'option `--allow-local-files`. Par exemple,

~~~bash
marp --theme my-theme.css --pdf --allow-local-files slide-deck.md
~~~

ou

~~~bash
marp --theme my-theme.css --pptx --allow-local-files slide-deck.md
~~~

**On ne peut pas inclure de vidéos dans un fichier PDF et donc dans un fichier pptx avec cette méthode.** Il vaut mieux uploader la vidéo sur une plateforme, par exemple Youtube et mettre un lien vers la vidéo.

### vers d'autres formats (XML, LaTeX, etc.)

Pour cela on peut passer par [la conversion HTML](#au-format-html) puis utiliser [pandoc](https://pandoc.org/index.html)

## Création d'un thème

On peut créer un thème dédié au projet directement en CSS `my-theme.css` et l'utiliser avec l'option `-theme`

~~~bash
marp --theme my-theme.css slide-deck.md
~~~

## Workflow

Watch les sources markdown avec un thème custom

~~~bash
marp --theme my-theme.css -w slide-deck.md
~~~

Exporter vers des images dans un fichier powerpoint

~~~bash
marp --theme my-theme.css --pptx slide-deck.md
~~~

Les notes seront bien affichées pour la personne qui fait la présentation

## Autoriser le markup HTML

Utiliser l'option `--html`

~~~bash
marp --html --theme my-theme.css -w slide-deck.md
~~~

## Points à eclaircir

- la directive _class
- import video et images
- gestion des videos et images dans le fichier pptx converti (est ce que la vidéo est présente et en mode lecture)

## Ressources

- [Marp écosystème](https://marp.app/)
- [Marpit framework](https://marpit.marp.app/), sur quoi est basé marp
- [Marpit API](https://marpit-api.marp.app/index.html)
- [Doc officielle Marp CLI](https://github.com/marp-team/marp-cli)
- [Produire un powerpoint editable dans le workflow de Marp](https://github.com/marp-team/marp/discussions/82), l'export vers pptx de marp ne cree pas une présentation éditable mais une version images. Pour produire un ppt éditable il faut passer par le format pdf avant
- [Pandoc](https://pandoc.org/index.html), un convertisseur de document universel et éprouvé
- [Convertisseur pdf vers powerpoint](https://pdf.online/pdf-to-powerpoint-converter), un outil de conversion en ligne gratuit permettant de convertir un fichier PDF vers un fichier pptx éditable

