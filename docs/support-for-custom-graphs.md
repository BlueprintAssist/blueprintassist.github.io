# Support For Custom Graphs 
1. Close and reopen the asset containing the graph. Check the the output log for the asset editor name. In the example below it is `BlueprintEditor`
![](https://i.imgur.com/9I6tRqf.png)

2. Open the Blueprint Assist settings and search for `Supported Asset Editors`, add the asset editor name to the list
![](https://i.imgur.com/XTdXUXg.png)

3. Close and reopen your asset again, if it worked successfully you will be able to see the Blueprint Assist toolbar. Click the toolbar and open the Debug Menu.
![](https://i.imgur.com/eidgsnf.png)

4. With the debug menu open, hover the graph and it should find the Graph Type. Write down this name (unfortunately copy-paste does not work right now)
![](https://i.imgur.com/1wd18QN.png)

5. Update the blueprint formatting settings depending on the style of graph

    5.1 If it is a Blueprint style graph, add the graph type to `Editor Preferences > Blueprint Formatting > Use Blueprint Formatting for These Graphs` 
![](https://i.imgur.com/NQQij9f.png)

    5.2 Otherwise, add the graph type to `Editor Preferences > Other Graphs > Non Blueprint Formatter Settings`. Set the direction of the graph (output if the graph executes right or input if the graph executes left).
![](https://i.imgur.com/DtS5a0Y.png)

6. Close and open your graph again and all plugins features should be enabled! 

If you would like this graph type to be always supported send me a message by creating an issue here or through the forums and I will add it in future versions of the plugin.

Make sure to send both the `Asset Editor Name` (in step 1) and the `Graph Type` (in step 4).