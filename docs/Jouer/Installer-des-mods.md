# Installer des mods

## R2MODMAN - Recommandé

!!! warning "Attention"
    En date du 01/05/2024, r2modman est en version 3.1.48 ! Cette versions ne supporte pas Lycans pour le moment. Néanmoins, la prochaine versions de r2modman ajoutera Lycans à la liste des jeux disponibles. En attendant cette version, il est nécessaire d'installer des mods manuellement.

R2modman est un manager de mod qui offre de nombreux avantages par rapport à une installation manuelle. Grâce à lui vous pouvez facilement :

- Installer et mettre à jour des mods et toutes leurs dépendances en un clic
- Désinstaller ou désactiver des mods
- Créer de multiples profils avec des mods différents
- Jouer facilement avec des mods ou en vanilla
- **Partager les mods que vous utilisez avez vos amis**

De plus, le plus grand avantage de r2modman par rapport à une installation manuelle : votre installation de Lycans reste propre, si vous lancez le jeu par Steam, ce dernier n'est pas affecté !

### Installation

Pour installer r2modman, rendez-vous sur la page de [release Github](https://github.com/ebkr/r2modmanPlus/releases), scrollez vers "Assets" et téléchargez le fichier `r2modman-Setup-X.X.X.exe` (où X.X.X correspond à la version de r2modman)

![image](https://github.com/lycans-modding/LMWiki/assets/15271735/488233b8-850d-4d0d-afda-595307025a45)

### Mise à jour

R2modman télécharge automatiquement les nouvelles mise à jours quand elles sont disponibles. Quand une mise à jour a été téléchargée, elle sera installée une fois que vous aurez fermer r2modman.

### Installer des mods

!!! danger "Attention"
    Tous les mods de Lycans sont dépendants de BepInEx ! La version actuelle de BepInEx sur Thunderstore (v5.4.21) doit être configurée afin de charger correctement les mods. Si vos mods ne marchent pas après installation, allez dans votre profil et cliquez sur "Config editor". Cliquez ensuite sur "BepInEx\config\BepInEx.cfg" et sur "Edit config". Scrollez jusqu'à l'option "Chainloader" et assurez-vous que l'option **HideManagerGameObject** ait la valeur `true`. ![image](https://github.com/lycans-modding/LMWiki/assets/15271735/be2ac491-98c4-47a9-93c6-960d8ad3db06)


Une fois que vous avez installer r2modman, vous devrez sélectionner "Lycans" dans la liste des jeux qui vous seront présentés. Cliquez sur "Select Game" : 

![image](https://github.com/lycans-modding/LMWiki/assets/15271735/8462525a-d08e-4e82-84a5-09b1f7efe6e3)

Vous devez ensuite créer un nouveau profil de jeu en cliquant sur le bouton "Create New" (ou utiliser le profil par défaut qui a été créé pour vous). Une fois que c'est fait, vous pouvez sélectionner un profil en cliquant sur "Select Profile" : 

![image](https://github.com/lycans-modding/LMWiki/assets/15271735/c27145a6-eb8e-4ad5-be8e-2c010cbdf699)

Quand ces étapes sont faites, vous pouvez installer un mod comme ceci : 

- Cliquez sur le bouton "Online", recherchez les mods qui vous intéressent dans la liste de tous les mods (vous pouvez modifier la manière dont est triée la liste des mods en cliquant sur la dropdown "Sort" en haut à droite). Quand vous avez sélectionné un mod, vous pouvez cliquer dessus, puis sur "Download" et enfin "Download with dependencies" et c'est tout. Vous pouvez voir vos mods installés dans le menu "Installed".

OU

- Cherchez un mod qui vous intéresse sur [Thunderstore](https://thunderstore.io/c/lycans/), cliquez sur le bouton "Install with Mod Manager". Cliquez sur "Ouvrir r2modman" si une fenêtre vous le demande (vous pouvez cocher la case pour que votre navigateur ne vous le demande plus à chaque fois) et c'est tout. Vous pouvez voir vos mods installés dans le menu "Installed" de r2modman.

### Mettre à jour les mods

Pour mettre à jours les mods, c'est encore une fois très simple : 

1. Ouvrez r2modman avec le profile que vous souhaitez mettre à jour
2. Scrollez tout en bas de la tab "All"
3. Cliquez sur "Update all" puis confirmez

![image](https://github.com/lycans-modding/LMWiki/assets/15271735/03c323f1-1f4a-4cd7-959a-5572eceb85b2)

### Configuration des mods

Certains mods disposent de configuration en jeu, mais la grande majorité vous sauvegarder le dossier "BepInEx\config". Vous pouvez modifier ces fichiers de deux façons :

**Avec r2modman**

1. Sélectionnez le profil avec les mods à configurer
2. Cliquez sur le bouton "Config Editor"
3. Cliquez sur le mod à configurer
4. Cliquez sur "Edit config"

**Manuellement**

1. Sélectionnez le profil avec les mods à configurer
2. Cliquez sur le bouton "Settings"
3. Sélectionnez la tab "Locations"
4. Cliquez sur le bouton "Browse profile folder"
5. Dirigez vous dans le dossier "BepInEx\config"
6. Editez le fichier de configuration pour le mod que vous souhaitez dans un éditeur de texte de votre choix (bloc note, notepad++, VSCode...)

### Lancer le jeu avec des mods

R2modman rends cette partie très simple, il suffit de : 

1. Sélectionnez le profil avec les mods
2. Cliquez sur le bouton "Start modded" en haut à gauche
3. Attendre que le jeu se lance

### Partager ses mods

Vous souhaitez partager la liste de vos mods avec vos amis pour pouvoir jouer ensemble simplement ? R2modman possède une fonctionnalité qui vous permet d'exporter et d'importer des profils avec tous leurs mods et leur configuration !

**Pour exporter**

1. Sélectionnez le profil à exporter
2. Cliquez sur "Settings" puis aller dans la tab "Profile"
3. Cliquez sur le bouton "Export profile as code"
4. Un code apparaît, vous pouvez l'envoyer à vos amis !

**Pour importer**

1. Si vous êtes déjà dans un profil, allez dans "Settings" > "Profile" > "Change profile"
2. Dans la liste des profils, cliquez sur "Import / Update"
3. Cliquez sur "Import new profile" si vous créez un nouveau profile et sur "Update existing profile" si vous en mettez-un à jour
4. Sélectionnez "From code"
5. Rentrez le code fourni et cliquez sur "Import"

## Installation manuelle - Non recommandé

Il est possible d'installer des mods manuellement, mais pour votre bien et celui des développeurs de mods, si vous ne savez pas ce que vous faites, il est fortement recommandé d'utiliser r2modman à la place !

Les mods de Lycans dépendent de [BepInEx](https://github.com/lycans-modding/BepInExPack-Lycans/releases/tag/5.4.2202) qui sert de mod loader pour fonctionner correctement. Nous allons voir comment l'installer sur Lycans et comment ajouter des mods tels que ceux disponibles sur [la page des mods](https://lycans-modding.github.io/LMWiki/Jouer/Liste-des-mods/).

### Pack BepInEx

Pour plus de facilité sur une installation manuelle, il est possible de télécharger directement un BepInEx préconfiguré qui inclus également [HookGenPatcher](https://thunderstore.io/c/lycans/p/LycansModding/HookGenPatcher/)

1. Rendez vous sur les [Release Github](https://github.com/lycans-modding/BepInExPack-Lycans/releases)
2. Cliquez sur le lien "BepInExPack-[version].zip" dans le menu déroulant "Assets"
3. Dans Steam, faites un clic droit sur Lycans puis "Gérer > Parcourir les fichiers locaux"
4. Vous pouvez extraire le contenu du fichier .zip que vous avez téléchargé dans le dossier "Lycans"

Votre installation doit ressembler à ceci à la fin de cette procédure :

![image](https://github.com/lycans-modding/LMWiki/assets/15271735/6a188875-8832-465b-aef9-9d8664bd2040)

Lancez Lycans depuis Steam, si tout s'est bien passé, vous devriez voir une console s'ouvrir juste avant Lycans :

![image](https://github.com/lycans-modding/LMWiki/assets/15271735/1d30cc0c-f41a-45a0-b607-e06994ddc643)

### Installer et mettre à jour des mods

Certains mods nécessitent d'autres mods pour fonctionner correctement. Vous pouvez le voir sur la page du mods dans la section "This mod requires the following mods to function". Il vous faudra donc télécharger toutes les dépendance d'un mod pour que ce dernier fonctionne correctement. À l'exception de BepInEx et de HookGenPatcher qui sont inclus par défaut dans le pack BepInEx.

![image](https://github.com/lycans-modding/LMWiki/assets/15271735/8edef301-2ca8-47b3-bcd3-643426be56f2)


1. Rendez vous sur [la page Thunderstore de Lycans](https://thunderstore.io/c/lycans/) pour télécharger les mods qui vous intéressent (cliquez sur "Manual download"
2. Rendez vous dans le dossier "steamapps\common\Lycans\BepInEx\plugins"
3. Créez un dossier pour le mod avant d'extraire le contenu du fichier ZIP que vous avez téléchargé.

L'opération est identique pour installer ou mettre à jour un mod.

### Désactiver les mods

Si vous souhaitez désactiver un mod en particulier, vous pouvez le supprimer du dossier "plugins"

Si vous souhaitez désactiver tous les mods, vous pouvez renommer le fichier "winhttp.dll" dans le dossier "Lycans" en "winhttp.dll.dis". Il suffit alors de le renommer à nouveau "winhttp.dll" pour réactiver les mods.

### Configuration des mods

Certains mods peuvent avoir une configuration accessible dans le dossier "steamapps\common\Lycans\BepInEx\config\\[nom du mod].cfg", vous pouvez modifier ces fichiers de config à l'aide de n'importe quel éditeur de texte (bloc note, notepad++, visual studio code...)

## Reporter un bug sur un mod

Afin de vous porter assistance avec un mod, un moddeur aura besoin d'un maximum d'informations sur votre problème. Voici une liste non exhaustive d'éléments que vous devriez réunir avant de reporter un bug : 

- Une description précise de ce que vous étiez en train de faire au moment où le bug s'est produit.
- D'éventuelles captures d'écran ou de vidéos présentant le problème
- **Un fichier "LogOutput.txt"**

Pour trouver le fichier LogOutput.txt, rendez vous dans le dossier "steamapps\common\Lycans\BepInEx".

Si le fichier est trop lourd pour la limite d'upload de Discord, vous pouvez le compresser dans une archive .zip.

Une fois que vous avez ces éléments à votre disposition, rendez vous dans le salon #support-technique sur le [Discord LYCANS MODDING](https://discord.gg/KjsvBDJwSV) et notifiez l'auteur du mod (si vous savez que c'est bien son mod qui pose problème) sinon attendez le passage d'une âme charitable qui pourra vous aider :)
