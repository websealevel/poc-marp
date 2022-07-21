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


### vers d'autres formats (XML, LaTeX, etc.)

Pour cela on peut passer par [la conversion HTML](#au-format-html) puis utiliser [pandoc](https://pandoc.org/index.html)

## Ressources

- [Marp écosystème](https://marp.app/)
- [Doc officielle Marp CLI](https://github.com/marp-team/marp-cli)
- [Produire un powerpoint editable dans le workflow de Marp](https://github.com/marp-team/marp/discussions/82), l'export vers pptx de marp ne cree pas une présentation éditable mais une version images. Pour produire un ppt éditable il faut passer par le format pdf avant
- [Pandoc](https://pandoc.org/index.html), un convertisseur de document universel et éprouvé
- [Convertisseur pdf vers powerpoint](https://pdf.online/pdf-to-powerpoint-converter)

