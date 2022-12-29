# Dataset Annotation Result

The annotation result of dataset is obtained by merging the annotation results of all the data under it. It doesn't need to be stored separately, so only the import/export cases need to be supported.

## **Single JSON file**

The annotation results of all data are merged into one large JSON file. This is suitable for situations where the amount of data is small, for example, the number of data does not exceed 1000.

1. Separate different types of information. For example, separating results and data information allows result information to adopt a simple flat structure, while data information can adopt a multi-layer structure (Frame series);
2. The Data ID and Class ID included in the JSON are all external IDs. Even internal IDs become external IDs once exported. When importing again, a new internal ID will be generated, and the original record cannot be overwritten. Various types of objects are associated through external IDs, such as the Class to which the Object belongs.

```json
JSON example
{
    // Version format
    "version": "1.0",
    // Dataset ID. Not required when importing.
    "datasetId": 1,
    // Dataset name. Not required when importing.
    "datasetName": "LiDAR Fusion Trial",
    // Export time. Not required when importing.
    "exportTime": "2022-11-22T06:12:13.447Z",
    
    // Classifications information, refer to the definition of Classification for the specific structure.
    "classifications": [],
    
    // Class information, refer to the definition of Class for the specific structure.
    "classes": [],
    
    // Data information, refer to the definition of Data for the specific structure.
    "data": [],
    
    // Result information, refer to the definition of Data Annotation Result for the specific structure.
    "results": []
}
```

## **Multiple JSON files**

For a Dataset with a large amount of data, if a single JSON file is used, the file will be very large, consume a lot of resources when opening, and even fail to open. In particular, the amount of data in the point cloud segmentation scene is even greater, so it is recommended to divide the JSON file by Data, and then pack it into a compressed package.

1. When importing results, data needs to be imported at the same time, and it is not supported to associate results with existing data;
2. For large data sets, only data information is exported, and data files are not exported. Otherwise, the compressed package will be very large, if necessary, you can download it according to the address in the data information;
3. The Frame Series structure is not preserved when exporting, because the Frame Series is only useful when labeling, and it is not required when using the result;
4. Import based on data information is not supported, because it takes a long time and is error-prone to download a large number of files from the network;
5. Considering that the data name may be repeated, the method of name + ID is used as the name of a single Data export file when exporting, and the ID can be ignored when importing, as long as the file name in this import is not repeated.

