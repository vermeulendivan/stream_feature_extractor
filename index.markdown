---
layout: home
title: Home
---

![qgis_ui](/images/ui/qgis_ui.png)

A QGIS plugin to extract stream features (wells, sinks, confluences, etc.) from a stream network. The plugin can be applied to vector layers which is of line geometry type, and can be either singlepart or multipart features. Once the processing is done the layer will be added to the QGIS canvas with a suitable symbology for each feature type.

The source code can be found [here](https://github.com/kartoza/stream_feature_extractor).

# Installation of the plugin
The easiest approach will be to install the plugin using the QGIS plugin manager:
1. In QGIS, go to Plugins > Manage and install plugins;
2. Select the All tab;
3. In the search bar, type 'stream feature extractor'; and
4. Select the plugin and click on the Install button.

![plugin_management](/images/ui/plugin_install.png)

# License
This plugin is Free and Open Source Software and is released under the GPL V2.
See the LICENSE file included with the plugin (and in this repository) for
more information about this license.
