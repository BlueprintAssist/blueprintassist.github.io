# FAQ

| Table of Contents |
| - |
| [Formatting looks off](#formatting-looks-off)
| [Building for a non supported UE version](#building-for-a-non-supported-ue-version)
| [Sharing plugin settings through source control](#sharing-plugin-settings-through-source-control)
| [Stop plugin from compiling when packaging](#stop-any-editor-plugin-from-building--compiling-when-packaging)
| [Support for custom graphs](#support-for-custom-graphs)

# Formatting looks off
Formatting has odd spacing / wires are misaligned. This is quite a common issue. The node size is calculated and saved when you open the graph or upon creating a new node. We don't know when the size of a node changes later! 

You can fix this by selecting the nodes and running the `RefreshNodeSize` command (`CTRL+SHIFT+R`).

![](https://i.imgur.com/swDgaxQ.jpg)

Most commonly this occurs even upon creating an event node. The event node spawns expanded because we are renaming the title, so we fail to calculate the size correctly upon creating. Make sure to refresh node size after creating your event nodes!

![](https://i.imgur.com/XrBj5gh.gif)

# Building for a non supported UE version

1. Download the plugin through the marketplace for a UE version you have currently have
2. Open the command prompt 
3. Run this command to build the plugin **(The command will not work if you use powershell!)**

> "**%UNREAL_DESIRED%**/Engine/Build/BatchFiles/RunUAT.bat" BuildPlugin -Plugin="**%UNREAL_CURRENT%**/Engine/Plugins/Markeplace/BlueprintAssist/BlueprintAssist.uplugin" -Package="**%OUT_LOCATION%**" -CreateSubFolder

Example: Building for desired version `UE_5.0` and our current version is `UE_4.27`.

> "**C:/Program Files/Epic Games/UE_5.0/Engine/Build/BatchFiles/RunUAT.bat**" BuildPlugin -Plugin="**C:/Program Files/Epic Games/UE_4.27/Engine/Plugins/Marketplace/BlueprintAssist/BlueprintAssist.uplugin**" -Package="**C:/TempBlueprintAssist**" -CreateSubFolder

4. Open `BlueprintAssist.uplugin` in a text editor (above, it will located at `C:/TempBlueprintAssist/BlueprintAssist/BlueprintAssist.uplugin`)
    * Set EngineVersion to your desired version `"EngineVersion": "5.0.0"`
5. Copy the built plugin from your package location (`C:/TempBlueprintAssist/BlueprintAssist`) into either your:
    * Project plugin location `%PROJECT_DIR%/Plugins`
    * Engine plugin marketplace folder `C:/Epic Games/UE_5.0/Engine/Plugins/Marketplace`

# Sharing plugin settings through source control

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

# Stop plugin from building / compiling when packaging

* Open your project's `.uproject` file and go to the plugins section. We need to set the `WhitelistTargets` to only the Editor.

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