# Changelog

### 4.1.0
* Add feature `Lock Node (ALT+L)`
    * Locked nodes will not move formatting. [See more](../features/command-list.md#toggle-lock-nodes)
* Add feature `Group Node (ALT+G | CTRL+ALT+G)`
    * Grouped nodes will move together on the graph. [See more](../features/command-list.md#group-nodes)
* Add setting `ApplyVariableDefaultsToEventDispatchers` (default: false)
* Add setting `DisableBlueprintAssistPlugin` (default: false)
* Fix issue with missing PlainBorder image

### 4.0.12
* Open workflow menu when pressing `SwitchWorkflowMode (ALT+O)` in AnimBP
* Fix issue with comment bubble bounds not being calculated correctly
* Fix issue with detecting node size changes when comment bubble is altered
* Fix issue with `AlwaysFormatAll` setting where camera would lerp after formatting

### 4.0.11
* Add setting `Cache Save Location`. Choose to save the cache file in the `Project/Saved` or `Plugin` folder.
* Fix missing `WidgetBlueprintEditor` in `SupportedAssetEditors` setting
* Fix undo not working for `AdditionalDragNode` and `GroupMovement` features
* Fix node size change not being detected when changing event nodes replication setting

### 4.0.10
* Change `DisconnectNodeExecution` hotkey to `ALT+D` (old `CTRL+D` is now used by Unreal for duplicate node)
* Fix issue where find search bar (`CTRL+F`) was not working correctly in the level editor in 5.1
* Fix bad pin alignment in 5.1
* Fix accessing stale ptrs on shutdown (issue #103)
* Fix warning messages related to uninitialized variables

### 4.0.9
* Fix compile issues with 5.1
* Fix issue #99 where FText pins were not being detected for size changes
* Fix issue #100 where auto-generated parent would overlap event node when auto-formatting is disabled

### 4.0.8
* Fix crash #95 when running selective formatting

### 4.0.7
* Fix issues #92 and #93 related to badly created reroute nodes

### 4.0.6
* Fix compile issues in UE5.1EA
* Add setting `AlignExecNodesTo8x8Grid` (disabled by default) ([issue #67](https://github.com/fpwong/BlueprintAssistWiki/issues/67))
* Add setting `FormatAllHorizontalAlignment`: Align the left-side of a node-tree either by containing `Comment` or by the `RootNode`
  * Set to `RootNode` by default (previously used `Comment`)
* Fix issue where node size change would not be detected if the pin's default object had changed
* Fix crash when formatting related to CommentUnder (issue #90)

### 4.0.5
* Improved look of overlay when caching nodes. Hide center progress bar if we only need to cache a few nodes.
* Fix issue with knot creation (issue #89)

### 4.0.4
* Added setting `Show Overlay When Caching Nodes` (enabled by default)
  * Shows a progress bar when caching node sizes on the graph
  * Also blocks the user from seeing the graph jump around when caching nodes as this can cause discomfort for photosensitive users
* Fix issue where the `Toggle Context Sensitive` command was not working

### 4.0.3
* Add hotkey to `Go To Parent Class Definition (CTRL + SHIFT + B)`
* Add setting for default category when generating getters and setters
  * See setting `Default Generated Setters Category` & `Default Generated Getters Category`
* Add feature `Go To Pin Class Definition` in the context menu for a pin (when you right click a pin)
* Add feature `Double Click Node Go To Definition` for Cast nodes
  * See setting `Enable Double Click Node Go To Definition` if you would like to disable this
* Implement comment padding for simple formatter (used for anim bp, metasound graph, material editor and more)

### 4.0.2
* Fix crash related to owning node (issue #88)
* Add support for Logic Driver plugin graphs
* Set default AutoFormatting behavior to `Never` on material graphs

### 4.0.1
* Added feature `Cut / Paste` for files & folders in the content browser
* Added feature `Focus Search Box (CTRL + F)` which gives keyboard focus to the search box in the focused tab
* Fix issue #86 compile issues when disabling precompiled headers
* Fix crash #87 when running dedicated server

### 4.0.0
* Reworked the comment padding and knot (reroute) creation algorithms (only on blueprint graphs)
* Added feature `Folder Bookmarks` for the content browser
  * Press `CTRL + SHIFT + {0-9}` while the content browser is focused to create a bookmark
  * `CTRL + {0-9}` to activate that bookmark
  * Change the hotkey in the setting `Folder Bookmarks`
* Rename shift dragging to `Group Drag Chords`. Default key is `SHIFT`.
* Reenable support for control rig graph in UE5
* Plugin now does not run when the game is playing in PIE and has focus
* Fix crash when opening certain asset editors (ILIAD plugin and runtime curve editor)
  * Added setting `Supported Asset Editors` so we don't try to add toolbar to invalid editors
* Fix issue where the function / variable defaults were not being applied

### 3.3.2
* Fix issue where users may see a solid color box around their selected pin
     * Rename setting `Pin Highlight Color` to `Selected Pin Highlight Color`
* Fix one off error when scrolling through BA filtered lists

### 3.3.1
* Fix crash when opening Material graph [#80](https://github.com/fpwong/BlueprintAssistWiki/issues/80)

### 3.3.0
* Changed how the selected pin is highlighted
   * If you see a solid box around your pins please change the setting `Pin Highlight Color` to a transparent color
   * Default color is `(0.6, 0.6, 0.6, 0.33)`
* Fix issue where moving selection in a BA filtered menu would be one off when moving selection upwards for the first time
* Fix Niagara graphs not being detected by the plugin in UE5
* Fix issue when converting variable get to set for local variables

### 3.2.18
* Added feature: Additional drag nodes chords, keys to simulate left mouse dragging on the graph editor. See setting `Additional Drag Nodes Chords`
* Added feature: Right click context menu option for converting variable nodes from `get to set` and `set to get`
* Added feature: Default function category / tooltip / private etc. See settings under `New Function Defaults` for more
* Fix crash when undoing generate variable getter and setter

### 3.2.17
* Fix issue where the Metasound Graph would reset the position of nodes on save after running node formatting

### 3.2.16
* Fix crash when opening `Switch Workflow Mode` menu for an AnimBP in UE5
* `Switch Workflow Mode` now toggles workflow when editing WidgetBP or Behaviour Trees
* Change default `Toggle Node` hotkey from `Control + Backslash` to `Control + Slash`

### 3.2.15
* Fix crash when formatting certain GameplayAbility nodes (Wait Target Data)
* Fix crash when accessing polygon editor tab
* Fix issue where toolbar button would be applied multiple times to certain assets

### 3.2.14
* Fix compile issues with UE5 preview (UE5 early access is no longer supported)
* Previously node's comment bubbles would be globally set to the same value (not pinned by default). This is now disabled by default. You can enable this via the settings `Enable Global Comment Bubble Pinned` and `Global Comment Bubble Pinned Value`.

### 3.2.13
* Fix issue #76 where plugin would cause cooking to fail (change plugin type to EditorNoCommandlet)

### 3.2.12
* `Swap Node` now swaps position of node even when auto-formatting is off
* Fix issue where changing windows would sometimes fail to detect that the active tab changed
* Fix issue #73 where toolbar command keyboard shortcuts were not being processed

### 3.2.11
* Moving nodes using the `select pin` command now ignores knot nodes
* Fix occasional crash on closing editor

### 3.2.10
* Remove Auto Insert Comment behaviour (is now included in the Auto Size Comment plugin)
* Fix issue where nodes would be centered if they are offscreen when you select them

### 3.2.9
* Improved node navigation: pressing left / right in the same direction as the selected pin will jump between nodes
* Removed setting `UseUObjects`, now is the default behaviour
* Newly created variable nodes are now selected on creation

### 3.2.8
* Fix issue with toolbar for old version of UE (4.26 and earlier)
* Potential fix for issue #65 when hitting ensure condition

### 3.2.7
* Set `bUseUObjects` to true by default (fix for Access Violation crash)
* Toolbar is now generated when a valid graph is opened (UE4.27 or later)
* Fix issue #64 where interface functions were able to be set to private

### 3.2.6
* Fix issue #62 crash when running duplicate nodes for each link `CTRL + SHIFT + V`
* Fix crash related to `TWeakPtr<FExtender>`
* Fix issue where hidden pins would be focused when selecting certain nodes

### 3.2.5
* Fix crash in UE4.26 and earlier when opening certain asset types

### 3.2.4
* Fix issue where the BlueprintAssist toolbar was not being created correctly

### 3.2.3
* Added setting to globally disable auto formatting `Globally disable auto formatting`
* Holding `SHIFT` in the Go to symbol menu and selecting an item will open in a new tab
* Disable support for control rig graph due to large number of issues
* Fix performance issue where expensive function was being called on mouse move
* Fix issue #58 where a newly created node from collapsing a graph would be incorrectly linked
* Fix issue #60 shift dragging behaviour was not working
* Fix issue #61 where enhanced input nodes were not recognized in the Go to synbol menu

### 3.2.2
* Disabled toolbar on unsupported files
* Setting `Apply comment padding` now works on non-blueprint graphs
* Fix issue #52 crash when formatting certain parameter node layout

### 3.2.1
* Fix issue #51
* Remove log message when opening Switch Workflow Menu
* Rename variable defaults settings, now prefixed with *Variable*

### 3.2.0

* Added improved comment formatting support, disabled by default but please try out the setting `Apply Comment Padding` (can be enabled in the toolbar)
    * Limitations include: no padding for parameter nodes or reroute nodes, does not apply to non-blueprint graphs
    * Removed old setting `Account For Comments`
* Added settings related to default function properties (see `New Function Defaults`)
* Added setting `Auto Zoom to Node Behavior`: Determines when the viewport will zoom to the newly created node `{ Never, Always, Outside Viewport (default) }`
* Added `Create asset menu` to create a new asset `CTRL + ALT + n`
* Added `Switch workflow mode` menu for AnimBP and WidgetBP `ALT + o` 
    * I realised there is a leftover debug message when opening this menu, this will be removed in the next update)
* Added `Focus Graph Panel` command, default unbound
* Added message log warning for nodes on the graph which are extremely far away
* Non-blueprint formatter settings are set via graph class name. See `Non Blueprint Formatter Settings`.
* Disable `Auto Insert Comment` behavior (it is now included in the AutoSizeComment plugin)
* Fix issue #50
* Fix issue where input events would be blocked when pressing escape
* Fix issue where a menu created when dropping a node (such as the Get / Set menu when dropping a variable) would be instantly closed due to changing focus
* Fix issue where the MessageLog module would be included when building the game for non-editor targets
    * Please read [this link](https://github.com/fpwong/BlueprintAssistWiki/wiki/FAQ#stop-any-editor-plugin-from-building--compiling-when-packaging) about disabling editor plugins when building your game
* Fix issues with EditDetailsMenu
### 3.1.4
* Fix issue #45
* Detecting issues with reroute nodes now occurs only when compiling the blueprint
* Fix issue where node size timeout notification would not timeout

### 3.1.3
* Add BlueprintAssist section to message log
* Empty reroute nodes are listed in the message log upon opening a graph and compiling
* Display bugged execution reroute nodes in the message log as errors (they have more than 1 linked output)
* Fix usage of USTRUCT variable for issue #37
* Fix issue assert for valid tab which would trigger upon closing a tab

### 3.1.2
* Fix issue #37 🙏

### 3.1.1
* Detect exec pins for Niagara / AnimGraph / ControlRig graphs
* Fix issue where shift drag node would be offset slightly
* Fix toggle node not reading initial state correctly
* Update node size when NodeEnabledState changes

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