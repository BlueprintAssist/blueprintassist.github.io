### 3.1.0

* Plugin now detects node size changes and refreshes size before formatting
    * Setting `CacheSizeWhenRequired` is renamed to `RefreshNodeSizeBeforeFormatting`, and is true by default
    * Old behavior of refreshing upon opening a graph or adding a new node is now disabled by default, enable via setting `DetectNewNodesAndCacheNodeSizes`
* Change Tab Switcher hotkey to `CTRL + SHIFT + Tab`
* Added ability to shift drag nodes to drag all connected nodes (disabled by default: see bEnableShiftDraggingNodes)
* Fix issues where graph would be locked due to ongoing transaction
* Fix issues with several commands on non-blueprint graph types
* Fix issue where the wrong root node would be selected when formatting

### 3.0.2

* Fix issue where check would be hit when compiling material
* Fix issue where certain non-bp graphs would lock after formatting
* Fix issue #41 where compiling data asset bp along while data asset would cause crash
* Fix issue where disconnecting exec links on a macro would cause crash

### 3.0.1

* Generating getters and setters for booleans now ignores the b prefix
* Setting `Auto-add parent node` is on by default now
* Fix issue #36 where opening level sequence would crash editor
* Potential fix for issue #37 where crash would occur while editing blueprints
* Fix crash when running certain commands on non-blueprint editors

### 3.0.0

* Added open window menu, easy method to open *most* editor windows: `Ctrl+Shift+K` (this replaces the open setting menu)
* Added tab switcher menu: `Shift+Tab`
* Added toggle fullscreen command: `Alt+Enter`
* Added feature: [generate getter / setter](https://github.com/fpwong/BlueprintAssistWiki/wiki/Features#generate-getter-and-setter). Right click on a variable, to see context menu action. [#22](https://github.com/fpwong/BlueprintAssistWiki/issues/22)
* Added [auto-set variable defaults](https://github.com/fpwong/BlueprintAssistWiki/wiki/Features#set-variable-defaults). Auto set variable properties when they are created.
* Added behavior: automatically update `Instance Editable` when you set `Expose on Spawn` to true on a variable
* Added behavior: automatically generate parent event call when possible
* Added live coding compile successful sound (disabled by default)
* Added invisible knot nodes (disabled by default)
* Added command rename selected node: `F2` on a selected variable or macro to rename it
* Added formatting setting `Expand Nodes Ahead of Parameters` (enabled by default)
* Removed create variable menu
* Numerous improvements to formatting
* Fix issue with sharing settings through source control: https://github.com/fpwong/BlueprintAssistWiki/wiki/Sharing-plugin-settings-per-project
* Fix compile issues with UE5
* Fixed issue with creating knot nodes [#32](https://github.com/fpwong/BlueprintAssistWiki/issues/32)
* Fixed issue with select variable menu [#28](https://github.com/fpwong/BlueprintAssistWiki/issues/28)
* Fixed issue with create symbol menu [#27](https://github.com/fpwong/BlueprintAssistWiki/issues/27)
* Fixed issue with undo not working correctly on comments [#23](https://github.com/fpwong/BlueprintAssistWiki/issues/23)
* Fixed issue with undo not working correctly when running format all on unlinked event nodes