# FAQ

## Formatting looks off

* The most common cause of this is due to the plugin using an incorrectly cached node size
* Try manually selecting the nodes and run the `RefreshNodeSize (CTRL+SHIFT+R)` command

---

## Building the plugin for a custom Unreal version

If you are familiar with powershell scripts and would like to migrate to a custom engine, check out [Xist's powershell script](https://github.com/XistGG/UnrealXistTools#migrateuemarketplacepluginps1) 

Otherwise you can follow the instructions below:

1. Download the plugin through the marketplace for a UE version you have currently have
2. Open the command prompt (I have had issues in the past with powershell)
3. Run this command to build the plugin
    
    `%UNREAL_DESIRED%/Engine/Build/BatchFiles/RunUAT.bat" BuildPlugin -Plugin="%UNREAL_CURRENT%/Engine/Plugins/Markeplace/BlueprintAssist/BlueprintAssist.uplugin" -Package="%OUT_LOCATION%" -CreateSubFolder`
    
    !!! example "Example: Building for version `UE_5.0` and our current version is `UE_4.27`"
    
        `C:/Program Files/Epic Games/UE_5.0/Engine/Build/BatchFiles/RunUAT.bat" BuildPlugin -Plugin="C:/Program Files/Epic Games/UE_4.27/Engine/Plugins/Marketplace/BlueprintAssist/BlueprintAssist.uplugin" -Package="C:/TempBlueprintAssist" -CreateSubFolder`

4. Open `BlueprintAssist.uplugin` in a text editor. Above it will be located at `C:/TempBlueprintAssist/BlueprintAssist/BlueprintAssist.uplugin`
    * Remove the line describing the `EngineVersion`
5. Copy the built plugin from your package location `C:/TempBlueprintAssist/BlueprintAssist` into either:
    * Project plugin location: `%PROJECT_DIR%/Plugins`
    * Engine marketplace folder: `C:/Epic Games/UE_5.0/Engine/Plugins/Marketplace`

---

## Sharing plugin settings through source control

Navigate to the plugin settings and click the `Set as Default` button. Follow the prompts that appear.

![](https://i.imgur.com/6U94F31.jpg)

The plugin settings will be saved to the file

* `{Project Folder}/Config/DefaultEditorPerProjectUserSettings.ini`

![](https://i.imgur.com/IPXN7EC.jpg)

* Add the file to source control (it may already have been added if you have source control enabled in Unreal Engine)
* If you wish to edit the settings as plain text, see the Blueprint Assist section within the file. It will look like this:

```
[/Script/BlueprintAssist.BASettings]
bAddToolbarWidget=True
PinHighlightColor=(R=0.200000,G=0.200000,B=0.200000,A=1.000000)
PinTextHighlightColor=(R=0.728000,G=0.364000,B=0.003000,A=1.000000)
...
```

---

## Stop plugin from building / compiling when packaging

* Open your project's `.uproject` file and go to the `Plugins` section. We need to set the `WhitelistTargets` to only contain `Editor`.

```
    "Plugins": [
        {
            "Name": "BlueprintAssist",
            "Enabled": true,
            "MarketplaceURL": "com.epicgames.launcher://ue/marketplace/content/9e895371fa3a471c87337860d6f341ff",
            "WhitelistTargets": [
                "Editor"
            ]
        }
    ]
```