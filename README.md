# Stream feature extractor

A QGIS plugin to extract stream features (wells, sinks, confluences etc.)
from a stream network. The easiest way to install this plugin is to use
the QGIS plugin manager to install it (just search for 'stream' in the
plugin manager).


Visit our [home page](https://github.com/kartoza/stream_feature_extractor) for more details.

This plugin is Free and Open Source Software and is released under the GPL V2.
See the LICENSE file included with the plugin (and in this repository) for
more information about this license.

# Feature definitions
There are 11 types of features which can be extracted from a stream network:

1. Crossing: When two lines cross each other.

![crossing](https://github.com/kartoza/stream_feature_extractor/blob/develop/help/source/static/crossing.png)

2. Pseudo node: A node that has one upstream and one downstream node. The node is superfluous as it can be represented by one line instead of two.

![pseudo_node](https://github.com/kartoza/stream_feature_extractor/blob/develop/help/source/static/pseudo_node.png)

3. Well: A node that has one upstream node and zero downstream nodes.

![well](https://github.com/kartoza/stream_feature_extractor/blob/develop/help/source/static/well.png)

4. Sink: A node that has no upstream node and one or more downstream nodes.

![sink](https://github.com/kartoza/stream_feature_extractor/blob/develop/help/source/static/sink.png)

5. Watershed: A node that has more than one upstream node and zero downstream nodes.

![watershed](https://github.com/kartoza/stream_feature_extractor/blob/develop/help/source/static/watershed.png)

6. Unseparated: Only one upstream node or only one downstream node and intersects with one or more other lines. Note that in the lines below, there is only one node under the star, the other line has no node at the position of the star.

![unseparated](https://github.com/kartoza/stream_feature_extractor/blob/develop/help/source/static/unseparated.png)

7. Unclear bifurcation: It has more than one upstream and more than one downstream node, but the number of upstream and downstream nodes are same.

![unclear_bifurcation](https://github.com/kartoza/stream_feature_extractor/blob/develop/help/source/static/unclear_bifurcation.png)

8. Tributary/Branch: It has more upstream nodes than downstream nodes. The minimum number of downstream nodes is one.

![branch](https://github.com/kartoza/stream_feature_extractor/blob/develop/help/source/static/branch.png)

9. Confluence: It has more downstream nodes than upstream nodes. The minimum number of upstream nodes is one.

![confluence](https://github.com/kartoza/stream_feature_extractor/blob/develop/help/source/static/confluence.png)

10. Segment center: Segment center is the linear center of a line. The tool finds the point in the line that has distance half of the length of the line.

![segment_center](https://github.com/kartoza/stream_feature_extractor/blob/develop/help/source/static/segment_center.png)

11. Self Intersection: Same with intersection (crossing), but this time the line intersects with itself.

![self_intersection](https://github.com/kartoza/stream_feature_extractor/blob/develop/help/source/static/self_intersection.png)

# Installation of the plugin
The easiest approach will be to install the plugin using the QGIS plugin manager:
1. In QGIS, go to Plugins > Manage and install plugins;
2. Select the All tab;
3. In the search bar, type 'stream feature extractor'; and
4. Select the plugin and click on the Install button.

![plugin_management](https://github.com/kartoza/stream_feature_extractor/blob/develop/help/source/examples/plugin_install.png)

# How to extract features
The plugin is user-friendly and extractions can be done as follows:
1. Load a vector line layer to QGIS;
2. Select the layer; and
3. Click on the stream feature extractor icon in the toolbar. The features will be extracted for the selected layer.

![icon](https://github.com/kartoza/stream_feature_extractor/blob/develop/help/source/static/toolbar_icon.png)

4. (optional method) Vector > Stream feature extractor > Extract stream features from current layer.

# Available options
Possible parameters or settings for the plugin can be set. Go to Vector > Stream feature extractor > Options. The following can be set:
1. Search distance: This is the distance used to determine if nodes converged or not. Note: The distance is calculated in map units of your stream network;
2. Show intermediate node count layer: An intermediate layer which were used to extract the feature is loaded to QGIS; and
3. Enabling this will submit errors to the server for debugging.

![options](https://github.com/kartoza/stream_feature_extractor/blob/develop/help/source/static/options_dialog.png)

# Contributing

If you would like to contribute an enhancement, bug fix, translation etc. to
this plugin, please make a fork of the repository on github at:

https://github.com/kartoza/stream_feature_extractor

Then make your improvements and make a github pull request. Please follow
the existing coding conventions if you want us to include your changes.

## This plugin was implemented by:

**Kartoza (Pty) Ltd.**
https://kartoza.com/

**Tim Sutton**
tim@kartoza.com

## Under subcontract to:

**Terrestris**
http://www.terrestris.de/

## This plugin was sponsored by:

**Landesbetrieb fuer Hochwasserschutz und Wasserwirtschaft Sachsen-Anhalt,**
Otto-von-Guericke-Strasse 5,
39104
Magdeburg, Germany.
