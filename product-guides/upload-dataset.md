---
description: Image, LiDAR and 2D & 3D Fusion LiDAR datasets format requirement
---

# ⛽ Upload Dataset

## Dataset Format

Datasets can be uploaded from the `local drive` and through`URLs`.

### **Image**

| Images data format requirement | <p>Image files in .jpg and .png are supported.<br></p><p>Compressed files (in .zip, .gzip, .tar format) can also be uploaded directly..</p> |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |

```Plain
.
├── image_0 // Image 0
│   ├── data1.jpg
│   └── data2.jpg
├── data // Data info, only for exporting, more details can reference "Data Info" section
│   ├── data1.json
│   └── data2.json
├── result // Annotation result, more details can reference "Data Annotation Result" section
│   ├── data1.json
│   ├── data1_image_0_segmentation.png 
│   ├── data2.json
│   └── data2_image_0_segmentation.png
└── scene_1 // Scene, the structure is similar to the root directory
│   ├── image_0
│   ├── ...
│   ├── data
│   └── result
```

The image dataset sample can be downloaded from [_here_](https://app.box.com/s/hskeiv45ie1q3l6wubte6vaphreh76z3).

> _This dataset is provided by_ [_PandaSet_](https://pandaset.org/) _- a high-quality open-source dataset for autonomous driving._

If you don’t see a supported data or file type that you want to upload, Join our [Slack community](https://join.slack.com/t/xtreme1io/shared\_invite/zt-1jhk36uzr-NpdpYXeQAEHN6rYJy5\_6pg).

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

### **LiDAR (Point Cloud)**

LiDAR dataset folder must be compressed and placed under the folder "**point\_cloud**" and data must be in **.pcd** format.

<table data-header-hidden><thead><tr><th width="295"></th><th></th></tr></thead><tbody><tr><td>LiDAR data format requirement</td><td><p>Folder name: <strong>lidar_point_cloud_0</strong></p><p>File format: <strong>.pcd</strong></p><p>Upload file: compressed files <strong>(</strong>in <strong>.zip, .gzip, .tar</strong> format<strong>)</strong></p></td></tr></tbody></table>

The LiDAR dataset sample can be downloaded from [_here_](https://basicai-asset.s3.amazonaws.com/docs/Open-source/LiDAR/LiDAR\_Basic\_with\_Scene.zip).

> _This dataset is provided by_ [_PandaSet_](https://pandaset.org/) _- a high-quality open-source dataset for autonomous driving._

If you don’t see a supported data or file type that you want to upload, Join our [Slack community](https://join.slack.com/t/xtreme1io/shared\_invite/zt-1jhk36uzr-NpdpYXeQAEHN6rYJy5\_6pg).

### **2D & 3D LiDAR Fusion**

2D & 3D LiDAR fusion dataset format requirement:

<table data-header-hidden><thead><tr><th width="188"></th><th></th></tr></thead><tbody><tr><td>Folder structure</td><td><p><strong>lidar_point_cloud_0</strong>: LiDAR data folder name</p><p><strong>camera_config</strong>: camera parameter files folder name </p><p><strong>camera_image_0</strong>: 1st set of image data folder name</p><p><strong>camera_image_1</strong>: 2nd set of image data folder name</p><p><strong>camera_image_2</strong>: 3rd set of image data folder name...</p><p><strong>camera_image_N</strong>: N+1th set of image data folder name</p><p><strong>scene_1</strong>:  scene folder contains multiple lidar data structures</p></td></tr><tr><td>File format</td><td><p>LiDAR file format: <strong>.pcd</strong></p><p>Image file format: <strong>.jpg</strong> and <strong>.png</strong></p><p>Camera parameter file format: <strong>.json</strong></p><p>Upload file: compressed files in <strong>.zip, .gzip, .tar</strong> format</p></td></tr></tbody></table>

All the same set of data must be placed in different folders with identical file names.

<figure><img src="../.gitbook/assets/fold-structure.png" alt=""><figcaption><p>Folder Structure Diagram</p></figcaption></figure>

The 2D & 3D LiDAR Fusion dataset sample can be downloaded from [_here_](https://basicai-asset.s3.amazonaws.com/docs/Open-source/LiDAR/LiDAR\_Fusion\_with\_Scene.zip).

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption><p>2D &#x26; 3D Fusion Dataset Example</p></figcaption></figure>

> _This dataset is provided by_ [_PandaSet_](https://pandaset.org/) _- a high-quality open-source dataset for autonomous driving._

### **Structure**

2D & 3D LiDAR Fusion dataset

<pre><code>├── camera_config // Camera config, more details can reference "Point Cloud Camera Config" section
│   ├── data1.json
│   └── data2.json
├── camera_image_0 // Camer image 0
│   ├── data1.jpg
│   └── data2.jpg
├── camera_image_1 // Camer image 1
│   ├── data1.jpg
│   └── data2.jpg
├── camera_image_2 // Camer image 2
│   ├── data1.jpg
│   └── data2.jpg
├── lidar_config // Lidar config
│   ├── data1.json
│   └── data2.json
<strong>├── lidar_point_cloud_0 // Lidar point cloud 0
</strong>│   ├── data1.pcd
│   └── data2.pcd
├── result // Annotation result, more details can reference "Data Annotation Result" section
│   ├── data1.json
│   ├── data1_lidar_point_cloud_0_segmentation.pcd
│   ├── data2.json
│   └── data2_lidar_point_cloud_0_segmentation.pcd
├── scene_1 // Scene, the structure is similar to the root directory
│   ├── camera_config
│       ├── data1.json
│       └── data2.json
│   ├── camera_image_0 // Camer image 0
│       ├── data1.jpg
│       └── data2.jpg
│   ├── lidar_point_cloud_0 // Lidar point cloud 0
│       ├── data1.pcd
│       └── data2.pcd
│   └── result
</code></pre>

### **Upload dataset with pre-annotation results**

LiDAR basic and 2D & 3D LiDAR Fusion support to upload datasets with pre-annotation results.

All JSON files must be placed under the`result` folder.

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

## Tutorial

{% embed url="https://www.youtube.com/watch?v=l4I5DAPqKno" %}
Tutorial Series: Upload Multisensory Data
{% endembed %}

### **Dataset License**

This dataset is provided by [PandaSet](https://pandaset.org/) - a high-quality open-source dataset for autonomous driving. These Datasets are provided to You under a Creative Commons Attribution 4.0 International Public License (“CC BY 4.0”).
