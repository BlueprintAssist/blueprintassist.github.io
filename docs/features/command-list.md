# Command List

| Feature                                                         |              Hotkey               |
|:----------------------------------------------------------------|:---------------------------------:|
| [Blueprint Assist hotkey menu](#blueprint-assist-hotkey-menu)   |          `CTRL+SHIFT+F1`          |
| [Open window menu](#open-window-menu)                           |          `CTRL+SHIFT+K`           |
| [Select pin](#select-pin)                                       |            `ArrowKeys`            |
| [Select node](#select-node)                                     |         `CTRL+ArrowKeys`          |
| [Shift camera](#shift-camera)                                   |         `SHIFT+ArrowKeys`         |
| [Open blueprint creation menu](#open-blueprint-creation-menu)   |               `Tab`               |
| [Format node](#format-node)                                     |                `F`                |
| [Format node selectively](#format-node-selectively)             |             `SHIFT+F`             |
| [Format all events](#format-all-events)                         |             `CTRL+R`              |
| [Delete and link](#delete-and-link)                             |            `SHIFT+DEL`            |
| [Cut and link](#cut-and-link)                                   |          `CTRL+SHIFT+X`           |
| [Connect unlinked pins](#connect-unlinked-pins)                 |                `Q`                |
| [Link nodes between wires](#link-nodes-between-wires)           |             `CTRL+Q`              |
| [Link to hovered pin](#link-to-hovered-pin)                     |          `CTRL+SHIFT+Q`           |
| [Split pin](#split-and-recombine-pin)                           |              `ALT+Q`              |
| [Recombine pin](#split-and-recombine-pin)                       |           `ALT+CTRL+Q`            |
| [Disconnect selected pin](#disconnect-selected-wire-or-pin)     |                `D`                |
| [Disconnect node execution](#disconnect-node-execution)         |              `ALT+D`              |
| [Disconnect all pins](#disconnect-all-pins)                     |           `ALT+SHIFT+D`           |
| [Toggle context sensitive](#toggle-context-sensitive)           |             `CTRL+T`              |
| [Swap node left/right](#swap-node)                              |      `CTRL+SHIFT+LEFT/RIGHT`      |
| [Swap connection up/down](#swap-connection)                     |       `CTRL+SHIFT+UP/DOWN`        |
| [Edit selected pin value](#edit-selected-pin-value)             |             `CTRL+E`              |
| [Switch workflow mode](#switch-workflow-mode)                   |              `ALT+O`              |
| [Edit details menu](#edit-details-menu)                         |          `CTRL+SHIFT+E`           |
| [Zoom to node tree](#zoom-to-node-tree)                         |             `CTRL+=`              |
| [Add Symbol menu](#add-symbol-menu)                             |          `CTRL+SHIFT+A`           |
| [Focus search box](#focus-search-box)                           |             `CTRL+F`              |
| [Go to symbol menu](#go-to-symbol-menu)                         |             `CTRL+G`              |
| [Select variable menu](#select-variable-menu)                   |          `CTRL+SHIFT+G`           |
| [Open file menu](#open-file-menu)                               |           `CTRL+Tilde`            |
| [Find in files menu](#find-in-files-menu)                       |           `CTRL+ALT+F`            |
| [Open context menu for pin](#open-context-menu-for-pin)         |             `CTRL+M`              |
| [Open context menu for node](#open-context-menu-for-node)       |          `CTRL+SHIFT+M`           |
| [Duplicate variable node](#duplicate-variable-node)             |          `CTRL+SHIFT+V`           |
| [Merge selected nodes](#merge-selected-nodes)                   |           `ALT+SHIFT+M`           |
| [Replace node](#replace-node)                                   |             `CTRL+H`              |
| [Toggle nodes](#toggle-nodes)                                   |             `CTRL+/`              |
| [Rename selected node](#rename-selected-node)                   |               `F2`                |
| [Edit Node Comment](#edit-node-comment)                         |            `SHIFT+F2`             |
| [Group nodes](#group-nodes)                                     |        `ALT+G, ALT+CTRL+G`        |
| [Toggle lock nodes](#toggle-lock-nodes)                         |              `ALT+L`              |
| [Toggle node purity](#toggle-node-purity)                       |             `CTRL+T`              |
| [Toggle node advanced display](#toggle-node-advanced-display)   |           `ALT+CTRL+A`            |
| [Expand selection in direction](#expand-selection-in-direction) | `SHIFT+Z (left), SHIFT+X (right)` |
| [Refresh Node Size](#refresh-node-size)                         |          `CTRL+SHIFT+R`           |
| [Navigate Tab History](#navigate-tab-history)                   |       `ALT+HOME`, `ALT+END`       |
| [Tab Switcher Menu](#tab-switcher-menu)                         |         `CTRL+SHIFT+TAB`          |
| [Go to parent class definition](#go-to-parent-class-definition) |          `CTRL+SHIFT+B`           |

---

## Blueprint Assist hotkey menu

* Open a menu which displays the hotkeys for the plugin `CTRL + SHIFT + F1`

![](https://i.imgur.com/EZSIgdv.png)
***

## Open window menu
* Search and open a menu or setting with `CTRL + SHIFT + K`

![](https://i.imgur.com/WJld0RN.gif)
***

## Select pin
* Use the `ArrowKeys` to move the selected pin

* Selecting a node will select the top-right execution pin

* You can also select a pin by left-clicking on it

![](https://i.imgur.com/Grx5k6h.gif)
***
## Select node
* Select a node using `CTRL + ArrowKeys`

![](https://i.imgur.com/a27GWt5.gif)
***
## Open blueprint creation menu
* Press `Tab` to open the blueprint creation menu. With a pin selected it will create the menu for the pin

![](https://i.imgur.com/qRXXN1X.gif)
***
## Format node
* With a node selected press `F` to format the block of nodes
* If the block of nodes has an event node, it will use it as the root node
* Two styles for parameters: 
    * `Helixing`: Parameter nodes are placed below 
    * `LHS (Left-hand side)`: Parameter nodes are placed on the LHS of the node
* There are commands to forcing a formatting style (unbound by default)
    * Format with Helixing
    * Format with LHS (left-hand side)
* Important settings:
    * `Treat delegates as execution pins (default: true)`: When disabled, this will ignore linked delegate pins (which are directly connected to custom events). You may want to disable this if you prefer your custom events to be manually positioned.
    * `Apply comment padding (default: true)`: Uses comment box bounds when formatting. Use this along with the AutoSizeComment plugin, otherwise disable this.
    * `Globally disable auto formatting`: Disable all auto formatting behaviour

![](https://i.imgur.com/RweXyxv.gif)
***
## Format node selectively
* With multiple nodes selected press `Shift + F` to format *only* the selected nodes
* If you have a single node selected, this command will selectively format the node tree to the right

![](https://i.imgur.com/xnyZeLo.gif)

***
## Format all events
* Press `CTRL + R` to format all event nodes on the graph
* See setting `Format All Style` to choose the method of layout:
    * `Simple`: Event nodes are sorted by height and placed in a single column
    * `Smart`: Dynamic columns are created by estimating the width of all linked nodes in the event and then sorted by height
    * `Node Type`: Columns are created based on the node type `{ SpecialRootNodes, ActorEvents, CustomEvents, InputEvents, ComponentEvents, OtherEvents }`
* Blocks can be reordered by moving the height of the event node above other blocks.

![](https://i.imgur.com/BExmivg.gif)

***
## Delete and link
* With node(s) selected press `SHIFT + DEL` to delete the nodes while preserving the links

![](https://i.imgur.com/Am3DkTn.gif)

## Cut and link
* Functionally the same as `Delete and Link` above but also copy the selected nodes to your clipboard 

***
## Connect unlinked pins
* With a node selected, press `Q` to connect unlinked pins to nearby nodes

![](https://i.imgur.com/4I8rSp5.gif)
***
## Link nodes between wires
* With a node selected, hover a wire or pin and press `CTRL + Q` to link the node

![](https://i.imgur.com/wqGY1sS.gif)
***
## Link to hovered pin
* Select a pin, then hover another pin and press `CTRL + SHIFT + Q` to link the two pins

![](https://i.imgur.com/fvDGTUQ.gif)
***
## Disconnect selected wire or pin
* Hover a wire or pin and press `D` to disconnect

![](https://i.imgur.com/fYB6eeX.gif)
***
## Disconnect node execution
* Select a node and press `ALT + D` to disconnect node execution

![](https://i.imgur.com/nm2P8Q9.gif)
***
## Disconnect all pins
* Select a node and press `ALT + SHIFT + D` to disconnect all pins

![](https://i.imgur.com/7RZ7Pj4.gif)
***
## Toggle context sensitive
* With the blueprint creation menu open, press `CTRL + T` to toggle context sensitive

![](https://i.imgur.com/DvEXUfx.png)
***
## Swap node
* With a node selected, press `CTRL + SHIFT + (Left / Right)` to swap the node execution left or right
* By default the swap node command will break looping connections which were created after swapping. See setting: `Blueprint Assist Advanced > RemoveLoopingCausedBySwapping`

![](https://i.imgur.com/lh0MhUQ.gif)

***
## Swap connection
* With a pin selected, press `CTRL + SHIFT + (UP / DOWN)` to swap the pin connection

![type:video](assets/SwapConnection.mp4)

***
## Edit selected pin value
* Press `CTRL + E` to start editing the value of the selected pin
* Pressing the hotkey again will move to the next editable value on the pin (for example when editing the Delta Location Vector)

![](https://i.imgur.com/o9nwFSc.gif)
***

## Switch workflow mode
* Press `ALT + O` to switch workflow mode. This is mainly for AnimBP, WidgetBP and BehaviorTrees
* In the AnimBP, it will open a menu since there are more than 2 modes to be selected from

***
## Edit details menu
* Pressing `CTRL + SHIFT + E` will bring up a menu with a list of variables in the Details panel
* Selecting an item in the menu will bring keyboard focus to that variable (boolean variables will be toggled)

![](https://i.imgur.com/369upI5.gif)
***
## Zoom to node tree
* Pressing `CTRL + Equals` will zoom to fit the node tree (all nodes connected to the current node)

![](https://i.imgur.com/VnpLdja.gif)
***
## Add Symbol menu
* Pressing `CTRL + SHIFT + A` will open a menu allowing you to add a new *graph*, *function* *macro*, *variable* or *event dispatcher*

![](https://i.imgur.com/FL6I9ry.png)

***
## Go to symbol menu
* Pressing `CTRL + G` will open a menu allowing you to bring viewport focus to any *function* / *macro* / *graph* / *event*

![](https://i.imgur.com/O201yCf.png)

***
## Focus search box
* Pressing `CTRL + F` will focus the first found search box
* Searches relative to the widget under your mouse cursor

![type:video](assets/FocusSearchBox.mp4)

***

## Open file menu
* Press `CTRL + Tilde` to quickly search and open files in the editor
* Allows for filtering for directory **A** and asset type **B**
* Uses the asset search plugin

![](assets/OpenFileMenu.jpg)

***

## Find in files menu
* Press `CTRL + ALT + F` to search through files in the editor. Useful for searching for blueprint nodes on graphs or pin values.  
* Allows for filtering via asset type and directory
* Uses the asset search plugin

![](assets/FindInFiles.jpg)

***
## Select variable menu
* Pressing `CTRL + SHIFT + G` will open a menu allowing you to focus a variable in the blueprint

![](https://i.imgur.com/17WMoOU.png)
***
## Open context menu for pin
* Pressing `CTRL + M` will bring up the pin actions for the selected pin

![](https://i.imgur.com/WIenOKK.gif)
***
## Open context menu for node
* Pressing `CTRL + SHIFT + M` will bring up the node actions for the selected node

![](https://i.imgur.com/UFeoR1M.gif)
***

## Duplicate variable node
* Pressing `CTRL + SHIFT + V` will duplicate a variable node for each of it's links

![](https://i.imgur.com/Ttm6kVR.gif)
***

## Merge selected nodes

* Pressing `ALT + SHIFT + M` will merge the selected nodes

![type:video](./assets/MergeSelectedNodes.mp4)

***

## Replace node
* Replace the selected node with a new node by pressing `CTRL + H`

![](https://i.imgur.com/i14zp6I.gif)
***

## Shift camera
* Move the camera using `SHIFT + Arrow Keys`
***

## Toggle nodes
* Disabled or enable selected nodes using `CTRL + \`

![](https://i.imgur.com/dBgFyyJ.gif)
***

## Split and recombine pin
* Split hovered or selected pin using `ALT + Q`
* Recombine using `ALT + CTRL + Q`  

![](https://i.imgur.com/r0W5Hqb.gif)
***

## Rename selected node
* Rename selected *variable* or *macro* by pressing `F2`

## Edit node comment
* Edit the text in a node comment bubble by pressing `SHIFT + F2`

![](https://i.imgur.com/x5vIOBz.gif)
***

## Group nodes
* Group nodes so they are locked and move together `ALT + G`
* Ungroup nodes with `ALT + CTRL + G`
* Holding down any key while dragging the nodes will stop the group movement

!!! note "Settings"
    * `OnlyDrawGroupOutlineWhenSelected` to only draw the outline when a node is selected
    * `DrawNodeGroupFill` to also highlight the nodes inside the group

![](./assets/GroupNodes.gif)
***

## Toggle lock nodes
* Lock nodes so they are ignored by the Blueprint Assist formatter `ALT + L`

!!! warning "Experimental"
    * Currently the formatter doesn't work very well with this. Any downstream nodes will also be ignored.
    * When using this I suggest you use `Selective Formatting (Shift+F)`

![](./assets/ToggleLockNodes.gif)
***

## Toggle node purity

* Toggle the execution pins on a node if applicable. Handles `Cast` and `Variable Get` nodes `ALT + SHIFT + G`

![type:video](./assets/ToggleNodePurity.mp4)
***

## Toggle node advanced display

* Toggle any advanced display pins on the node. Most commonly used for the `Print String` node `ALT + CTRL + A`

![type:video](./assets/ToggleNodeAdvancedDisplay.mp4)
***

## Expand selection in direction

* Using the **hovered node** as the root, expand the selection in the direction
* `Shift + Z` for Left, `Shift + X` for Right
 
![type:video](./assets/ExpandSelectionLeftRight.mp4)
***

## Refresh node size

* In order for the plugin to work correctly, we must save the size of node. However there may be cases where the plugin fails to detect a size change.
  If your blueprint graph has overlapping nodes it is likely due to this.

* Select the incorrect nodes (I suggest simply selecting all the linked nodes) and press `CTRL + SHIFT + R` to refresh the sizes

* If you still have formatting issues, please report this [on github](https://github.com/fpwong/BlueprintAssistWiki/issues)
***

## Navigate tab history

Works the same as pressing the thumb buttons on your mouse to go back / forward in tab history

Only for Blueprint Graphs. Do not rebind to use CTRL in the keyboard shortcuts, it will not work!

* Go Forward in Tab History `ALT + HOME`
* Go Back in Tab History `ALT + END`

***

## Tab Switcher Menu

* Open a menu where you can navigate the editor's open tabs with `CTRL+SHIFT+TAB`
***

## Go to Parent Class Definition

* Navigate to the current asset's parent class in the Unreal or code editor with `CTRL + SHIFT + B`