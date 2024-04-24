# Publier un mod

Le contenu de cette page a été traduit et adapté en partie depuis le [wiki de r2modman](https://github.com/ebkr/r2modmanPlus/wiki/Structuring-your-Thunderstore-package)

## Packager son mod pour Thunderstore

La première étape pour publier un mod sur Thunderstore est de créer un dossier afin de packager le contenu de votre mod. Un exemple de package se trouve dans le [template de mod Lycans](https://github.com/lycans-modding/LycansModTemplate/tree/main/Thunderstore).

**Important:** Pour qu'un package soit considéré comme étant valide par Thunderstore, ce dernier doit contenir au moins les fichiers suivants : 

- Un fichier `README.md`
- Une image `icon.png`
- Un fichier `manifest.json`

Par défaut, les dossiers sont ignorés par Thunderstore et tout est remonté à la racine du dossier "plugins" dans le dossier BepInEx. Il est cependant possible de créer des dossiers spéciaux pour vous assurer que vos fichiers sont placés là où vous vous y attendez.

Si vous avez besoin de charger des ressources depuis un dossier spécifique, vous pouvez le faire comme ceci :
```cs
Path.Combine(Path.GetDirectoryName(Plugin.Info.Location), "MySubDirectory", "MyImage.png")
```

**Liste des dossier spéciaux pour Thunderstore :**

- plugins
- monomod (Si le nom d'un plugin se termine par `.mm.dll`, il sera installé dans ce dossier)
- patchers
- core
- config

À l'exception du dossier `/config`, tous les autres fichiers sont placés dans un dossier au format `NomAuteur-NomMod` afin d'éviter les risques de collisions dans le nom des mods (uniquement dans le cas d'un téléchargement avec r2modman).

Par exemple, un fichier .zip qui a la structure suivante :
```
# Mod.zip
  - <Fichiers requis>
  - patchers
    - MonPatcher.dll
  - un_dossier
    - Test.dll
    - un_autre_dossier
      - AutreTest.dll
  - plugins
    - monomod
      - ExemplePM.dll
  - monomod
    - MonMonomod.dll
```

Sera interprété et installé comme ceci par Thunderstore et r2modman :
```
# <profile>/BepInEx/
  - patchers
    - <NomAuteur-NomMod>
      - MonPatcher.dll
  - plugins
    - <NomAuteur-NomMod>
      - <Fichiers requis>
      - Test.dll
      - AutreTest.dll
      - monomod
        - ExemplePM.dll
  - monomod
    - <NomAuteur-NomMod>
      - MonMonomod.dll
```

## Publier le package sur Thunderstore

Une fois que vous avez créer votre fichier .zip, rendez vous sur le [Thunderstore de Lycans](https://thunderstore.io/c/lycans/)

1 - Connectez vous en cliquant sur le lien en haut à droite :

![image](https://github.com/lycans-modding/LMWiki/assets/15271735/135202f4-5ff8-42b0-bdad-97056619df84)

2 - Rendez vous en suite dans "settings" puis dans "Teams" : 

![image](https://github.com/lycans-modding/LMWiki/assets/15271735/ff72fd43-30dc-4101-b48a-df9da0eff011)

3 - Cliquez sur "Create Team", écrivez le nom avec lequel vous souhaitez distribuer vos plugins (votre pseudo, nom de votre équipe de dev, etc...)

4 - Rendez vous sur ["Upload"](https://thunderstore.io/c/lycans/create/). Dans "Team", renseignez le nom de l'équipe que vous venez de créer et dans "Communities" **assurez vous de sélectionner Lycans**, sans quoi, votre mod ne sera pas uploadé dans la liste des mods pour le jeu. Vous pouvez enfin sélectionner les tags qui correspondent à votre mod et sélectionner/glisser déposer votre fichier .zip avant de cliquer sur "Submit".

![image](https://github.com/lycans-modding/LMWiki/assets/15271735/981afe20-79de-4893-ab50-b2d49bb8f950)

En cas de problème pour uploader un mod, vous pouvez demander de l'aide sur le [Discord de Thunderstore](https://discord.thunderstore.io/) (anglais)