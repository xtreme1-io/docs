# Folder Structure

## Point Cloud Dataset Folder Structure

```json
.
├── camera_config // Camera parameter
│   ├── 00-1.json
│   └── 01-2.json
├── image0 // Camera 0 image
│   ├── 00-1.jpg
│   └── 01-2.jpg
├── image1 // Camera 1 image
│   ├── 00-1.jpg
│   └── 01-2.jpg
├── image2 // Camera 2 image
│   ├── 00-1.jpg
│   └── 01-2.jpg
├── point_cloud // Point cloud
│   ├── 00-1.pcd
│   └── 01-2.pcd
├── scene1 // Frame series (Not available on Xtreme1 open source version). Its structure refers to the root directory.
├── result // Annotation results. Its structure refers to the Data Annotation Result page.
     ├── 00-1.json
     └── 01-2.json
```

## Image Dataset Folder Structure

```json
.
├── image // Image dataset
│   ├── 00-1.jpg
│   └── 01-2.jpg
├── scene1 // Object tracking. Its structure refers to the root directory.
└── result // Annotation results. Its structure refers to the Data Annotation Result page.
     ├── 00-1.json
     └── 01-2.json
```

Data

```json
.
├── data // Data info. Its structure refers to the Data page.
│   ├── 00-1.json
│   └── 01-2.json
└── result // Annotation result. Its structure refers to the Data annotation result page.
     ├── 00-1.json
     └── 01-1.json
```

