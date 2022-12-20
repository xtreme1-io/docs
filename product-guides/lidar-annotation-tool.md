---
description: >-
  This article describes how to use 2D & 3D Fusion and Frame Series tool. The
  object tracking is a key-feature of the perception system of autonomous cars
  and ADASs.
---

# 🛣 LiDAR Annotation Tool

## LiDAR Annotation Tool Overview

The main screen of the LiDAR annotation tool consists of the following parts

<figure><img src="../.gitbook/assets/pc-interface.png" alt=""><figcaption><p>LiDAR Annotation Tool Interface</p></figcaption></figure>

****

****

****

**Settings**

* There are many settings in s that can help annotators better identify objects. For example, by displaying the intensity value of points, changing the size of points, etc.

****

**Results**

* Annotated object results will be displayed here. The label can be found through filters.

**Data Info**

* to display the information of the dataset.

<table data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td></td><td><p><strong>Tools</strong></p><ul><li>To create and adjust cuboids;</li><li>To project b-box/2d cuboid to 2D images;</li><li>To run a model to predict results</li></ul></td><td></td></tr><tr><td></td><td><p><strong>2D Camera Data</strong></p><ul><li>to project b-box/2d cuboid on 2d image;</li><li>If it is not a 2D &#x26; 3D Fusion dataset, 2d images are used for reference, helping to identify objects that are not clear in 3D.</li></ul></td><td></td></tr><tr><td></td><td><p><strong>Point Cloud Data</strong></p><ul><li>to annotate objects according the model training requirement;</li><li>AI-assisted tool can precisely make the cuboid fit on the object</li></ul></td><td></td></tr><tr><td><p><strong>Settings</strong></p><ul><li>There are many settings that can help annotators better identify objects. </li><li>For example, enlarging the point size allows annotators to more accurately identify objects with sparse point clouds.</li></ul></td><td></td><td></td></tr><tr><td></td><td><p><strong>Point Cloud Data</strong></p><ul><li>To annotate objects according the model training requirement;</li><li>AI-assisted tool can precisely make the cuboid fit on the object</li></ul></td><td></td></tr><tr><td></td><td><p><strong>Cuboid Views</strong></p><ul><li>When a cuboid is created on 3D point cloud data area, minor adjustments are usually made here to make the cuboid fit as closely as possible to the target object.</li></ul></td><td></td></tr></tbody></table>











