# Assemblys de référence

Afin de créer des mods pour Lycans, il vous faudra référencer plusieurs fichiers `.dll`.

Quelques exemples d'assemblys qui seront utilisées par au moins 80% des mods : 

- `Assembly-CSharp.dll` qui contiens le code du jeu.
- `BepInEx.dll` qui contiens les class nécessaires pour créer un mod.

Si vous voulez utiliser une librairie, il vous faudra une référence vers cette dernière. Ces références permettent au compilateur de savoir où trouver les composants nécessaires afin de compiler correctement votre mod sans erreur.

**Visual Studio 2022**

Pour ajouter une référence d'assembly sous Visual Studio, il suffit, après avoir créer un projet, de faire un clic droit sur "Dépendances" dans la liste des fichiers du projet. Il est aussi possible de faire un clic droit directement sur le projet puis de faire "Ajouter > Référence d'assembly"

Alternativement, il est aussi possible d'utiliser [Nuget](https://www.nuget.org/) pour récupérer ces références. Cette solution est d'ailleurs recommandée car elle facilite grandement le développement de mods.

- En cas de mise à jour du jeu, vous n'avez qu'à mettre à jour le package nuget pour pouvoir modder sur la dernière version
- Vous n'avez pas besoin de gérer vous-même le fait de stripper et de publicizer les DLL

## Stripping

Le principe de stripper une DLL permet de créer un fichier qui ne contiens que les entêtes des fonctions et le corps des classes sans conserver le contenu des fonctions. De ce fait, le code du jeu n'est **jamais** mis à disposition, et les moddeurs ont accès à une API qu'ils peuvent utiliser pour compiler leurs mods.

## Publicizing

En architecture logiciel, il est bon de restreindre le scope d'accès à certaines fonctions ou propriétés de classes à l'aide de mutateurs comme `internal` ou `private`. Malheureusement, dans le cas du modding, on est souvent amenés à vouloir modifier le comportement interne d'une classe. Il est alors souvent nécessaire de modifier des valeurs ou des fonctions avec un accès privé.

Pour ce faire, il y a une première solution qui consiste à s'appuyer sur le système de Réflexion en C#. Malheureusement, ça signifie que l'on doit utiliser des chaînes de caractères un peu partout dans notre code et que le compilateur est incapable de nous aider avec les types. Ce qui force donc à faire des cast et des vérifications dans tous les sens pour s'assurer de ne pas faire crash le jeu : 

```cs
// Exemple : Obtenir une référence sur un dropdown privé avec de la Réflexion
GameSettingsUI ui = GameManager.Instance.gameUI.GetComponent<GameSettingsUI>();
Type type = ui.GetType();
FieldInfo field = type.GetField("alchemistsCountDropdown", BindingFlags.NonPublic | BindingFlags.Instance);

// On est enfin capable de récupérer notre dropdown !
var dropdown = field.GetValue(ui) as TMP_Dropdown;
```

On voit très bien que le code manque de clareté. De plus, une erreur dans l'écriture de `alchemistsCountDropdown` et c'est le crash ! 

Heureusement, en manipulant une assembly, il est possible de modifier ses métadonnées pour rendre les membres publiques. Ainsi on peut récupérer la même dropdown comme ceci : 

```cs
GameSettingsUI ui = GameManager.Instance.gameUI.GetComponent<GameSettingsUI>();

// Beaucoup mieux :)
var dropdown = ui.alchemistsCountDropdown;
```

## Installer les librairies

Dans Visual Studio, faites un clic droit sur votre projet ou sur votre solution puis cliquez sur "Gérer les package NuGet". Dans la fenêtre qui s'ouvre, assurez vous que la source de package (en haut à droite) soit définie sur "Tout" ou sur "nuget.org". Puis, dans l'onglet "Parcourir", recherchez "Lycans". Voud devriez voir les packages suivants : 

![image](https://github.com/lycans-modding/LMWiki/assets/15271735/1357ce4d-c23d-4b3e-91b0-08d446178785)

- `Lycans.GameLibs` contiens les librairies strippées et publicizées de Lycans afin que vous ayez accès à une API de modding
- `MMHOOK.Lycans` contiens une librairie MMHOOK qui permet d'exécuter votre code avant, après ou à la place des fonctions de base de Lycans

Alternativement, vous pouvez ajouter manuellement les lignes suivantes parmi vos dépendances dans votre fichier `.csproj` : 
```xml
<PackageReference Include="Lycans.GameLibs" Version="0.10.0" />
<PackageReference Include="MMHOOK.Lycans" Version="0.10.0" />
```