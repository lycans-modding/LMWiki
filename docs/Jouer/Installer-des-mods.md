# Installer des mods

## Installation manuelle

Pour le moment, le seul moyen d'installer des mods est de procéder de manière manuelle. C'est loin d'être l'idéal, mais avec un peu d'intérêt de la part de la communauté, il sera à l'avenir possible d'être intégré à un mod manager tel que r2modman.

La plupart des mods devraient requérir [BepInEx](https://github.com/lycans-modding/BepInExPack-Lycans/releases/tag/5.4.2202) qui sert de mod loader pour fonctionner correctement. Nous allons voir comment l'installer sur Lycans et comment ajouter des mods tels que ceux disponibles sur [la page des mods](https://lycans-modding.github.io/LMWiki/Jouer/Liste-des-mods/).

### BepInEx
1. Rendez vous sur les [Release Github](https://github.com/lycans-modding/BepInExPack-Lycans/releases)
2. Cliquez sur le lien "BepInExPack-[version].zip" dans le menu déroulant "Assets"
3. Dans Steam, faites un clic droit sur Lycans puis "Gérer > Parcourir les fichiers locaux"
4. Vous pouvez extraire le contenu du fichier .zip que vous avez téléchargé dans le dossier "Lycans"

Votre installation doit ressembler à ceci à la fin de cette procédure :

![image](https://github.com/lycans-modding/LMWiki/assets/15271735/6a188875-8832-465b-aef9-9d8664bd2040)

Lancez Lycans depuis Steam, si tout s'est bien passé, vous devriez voir une console s'ouvrir juste avant Lycans :

![image](https://github.com/lycans-modding/LMWiki/assets/15271735/1d30cc0c-f41a-45a0-b607-e06994ddc643)

### Installer et mettre à jour des mods

1. Rendez vous sur [la page des mods](https://lycans-modding.github.io/LMWiki/Jouer/Liste-des-mods/) pour télécharger ceux qui vous intéressent
2. Rendez vous dans le dossier "steamapps\common\Lycans\BepInEx\plugins"
3. Si le mod que vous avez téléchargé est un fichier .zip, vous pouvez extraire son contenu dans le dossier "plugins", s'il s'agit d'un fichier .dll, vous pouvez le déposer directement dans le dossier "plugins".

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
