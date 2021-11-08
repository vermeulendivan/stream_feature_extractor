---
layout: page
title: User guide
permalink: /guide/
---

# How to extract features
The plugin is user-friendly and extractions can be done as follows:
1. Load a vector line layer to QGIS;
2. Select the layer; and
3. Click on the stream feature extractor icon in the toolbar. The features will be extracted for the selected layer.

![icon](/images/ui/toolbar_icon.png)

- (optional method) Vector > Stream feature extractor > Extract stream features from current layer.

# Intermediate layer
Intermediate layer is a temporary layer that is used for helping the tool to identify the nodes. You can show it when you run the tool by check the option
in options dialog.

If you open the attribute table of this intermediate layer, you will find something like this:

![intermediate_layer](/images/ui/intermediate_layer.png)

How the plugin creates the intermediate layer:
1. For each line in input layer, the tool will retrieve the first and the last
   vertex. The first one will be assigned as upstream node,
   and the last one will be assigned as downstream node for *node_type*. We
   also add the *line_id* as the attribute of the nodes;
2. The tool will find the nearby nodes for each nodes according to their type
   and add their id on the attributes (*up_nodes* and *down_nodes*);
3. The tool add another attributes, up_num and down_num. Basically,
   they represent the number of nearby upstream nodes and downstream nodes
   respectively. We will add 1 to *up_num* if the node is upstream_node,
   this applies for *down_num*; and
4. The tool will populate each node type based on the rules in :doc:`/features`.

# Available options
Possible parameters or settings for the plugin can be set. Go to Vector > Stream feature extractor > Options. The following can be set:
1. Search distance: This is the distance used to determine if nodes converged or not. Note: The distance is calculated in map units of your stream network;
2. Show intermediate node count layer: An intermediate layer which were used to extract the feature is loaded to QGIS; and
3. Enabling this will submit errors to the server for debugging.

![options](/images/ui/options_dialog.png)
