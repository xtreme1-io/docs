# Data Annotation Result

Since the annotation results are stored at the granularity of data, the data annotation result format needs to support both internal storage and import/export scenarios.A data may be labeled by multiple sources, and the labeling results need to be distinguished by source.

1. Object means Cuboid, and each Cuboid belongs to a certain Tracking Object. Note that a Tracking Object in a single frame may also contain multiple Cuboids (such as LiDAR-camera fusion dataset). The Object ID is UUID;
2. The import/export is based on the internal storage format, but the information used only internally, such as meta info, is removed;
3. Some information is not used when importing, but is needed for internal storage, it will be automatically added when importing, such as Object id, version, createdBy, createdAt, etc. Conversely, some redundant information is not stored in the internal storage, but needs to be added when exporting;&#x20;
4. Point cloud segmentation needs to store the point information in a separate file, and record the file URL in JSON to avoid JSON being too large. When importing/exporting, if the file is divided by Data, the point information can be directly placed in the file.

```json
JSON example
{
    // Format version
    "version": "1.0",
    // Data ID. Not required when importing.
    "dataId": 1,
    // Source ID. Not required when importing.
    "sourceId": 1,
    // Result source type. It can only be EXTERNAL related type when importing
    // DATA_FLOW, TASK, MODEL, EXTERNAL_GROUND_TRUTH, EXTERNAL_MODEL
    "sourceType": "TASK",
    // SourceName
    "sourceName": "20221009000000",
   
    // Validity. Currently, not supported for importing.
    "validity": "VALID",
    
    // Category attribute value. 
    //If provided during import, relevant category information must be provided at the outer layer to create a new one.
    "classificationValues": [
        {
            // Type ID
            "id": 1,
            // Category value. Each layer of attributes and their values form a node, 
            // and the parent-child relationship is established between nodes through pid (attribute ID) and pvalue (attribute value)
            "values": [
                {
                    // Property ID
                    "id": "64a16626-153f-4136-b7b4-572c10db08c3",
                    // ID of the parent attribute. If it is null, it is the root node.
                    "pid": null,
                    // It is only used when the parent attribute value is multi-choice, 
                    //and it is used to indicate which value is associated
                    "pvalue": null,
                    "name": "Make",
                    "type": "RADIO",
                    "value": "Mercedes-Benz",
                    "alias": "Manufacture",
                    // Whether it is a leaf node, note that it may be a non-leaf node in the definition.
                    "isLeaf": false
                },
                {
                    "id": "0fcb5add-4d2a-4d15-85e7-a8db966e6178",
                    "pid": "64a16626-153f-4136-b7b4-572c10db08c3",
                    "pvalue": null,
                    "name": "Model",
                    "type": "RADIO",
                    "value": "GLE450",
                    "alias": null,
                    "isLeaf": false
                },
                {
                    "id": "69607032-9b53-4c95-90a8-6e378c19aa08",
                    "pid": "0fcb5add-4d2a-4d15-85e7-a8db966e6178",
                    "pvalue": null,
                    "name": "Color",
                    "type": "RADIO",
                    "value": "Black",
                    "alias": null,
                    "isLeaf": true
                },
                {
                    "id": "24ce829b-9b60-4b88-99f7-379b144a3cb3",
                    "pid": "64a16626-153f-4136-b7b4-572c10db08c3",
                    "pvalue": null,
                    "name": "Type",
                    "type": "RADIO",
                    "value": "Sedan",
                    "alias": null,
                    "isLeaf": true
                },
                {
                    "id": "0669d8b1-f175-4f46-a8d2-cea7bf9dc1e2",
                    "pid": "64a16626-153f-4136-b7b4-572c10db08c3",
                    "pvalue": null,
                    "name": "Motor",
                    "type": "MULTI_SELECTION",
                    "value": ["Gas", "Electric"],
                    "alias": null,
                    "isLeaf": false
                },
                {
                    "id": "9c0d296f-7141-4fd9-9cbe-c3d96a93d411",
                    "pid": "0669d8b1-f175-4f46-a8d2-cea7bf9dc1e2",
                    "pvalue": "Gas",
                    "name": "Engine Capacity",
                    "type": "RADIO",
                    "value": "2.0L",
                    "alias": null,
                    "isLeaf": true
                },
                {
                    "id": "8e790d10-9931-43f6-82bb-60619f1a25ea",
                    "pid": "0669d8b1-f175-4f46-a8d2-cea7bf9dc1e2",
                    "pvalue": "Electric",
                    "name": "Capacity",
                    "type": "RADIO",
                    "value": "20～50kWh",
                    "alias": null,
                    "isLeaf": true
                }
            ]
        }
    ],
    
    // object (cubild) list
    "objects": [
        // 3D Cuboid
        {
            // ID. Not required when importing. 
            // It will be automatically filled.
            "id": "6ec0bd7f-11c0-43da-975e-2a8ad9ebae0b",
            // Tool type
            // 3D_BOX, 2D_RECT, 3D_SEGMENT_POINTS, 3D Segmentation
            "type": "3D_BOX",
            // Updated version. Initial value is 0.
            // Each change increases by 1.
            // Not required when importing. It will be automatically filled when exporting.
            "createdBy": 1,
            // Created time.
            // Not required when importing. It will be automatically filled when exporting.
            "createdAt": "2012-03-29T10:05:45Z",
            
            3D Object Tracking (Frame series) is NOT available on Xtreme1 open source version.
            // Tracking ID
            "trackId": "J0lkBP7r",
            // Track object name
            "trackName": "Car 1",

            // Category ID. If provided during import, relevant category information must be provided in the outer layer to create a new one
            "classId": 1,
            // Class name
            // Not required when importing. It will be automatically filled when exporting.
            "className": "Car",
            // Class attribute value. Similar to Classification, does not support multi-level nesting.
            "classValues": [
                {
                    "id": "bdc9acdf-4337-42de-8964-a1b5b6820287",
                    "pid": null,
                    "pvalue": null,
                    "name": "Made",
                    "type": "RADIO",
                    "value": "Mercedes-Benz",
                    "alias": "Manufacture",
                    "isLeaf": true
                },
                {
                    "id": "0fcb5add-4d2a-4d15-85e7-a8db966e6178",
                    "pid": null,
                    "pvalue": null,
                    "name": "Model",
                    "type": "RADIO",
                    "value": "GLE450",
                    "alias": null,
                    "isLeaf": true
                },
                {
                    "id": "24ce829b-9b60-4b88-99f7-379b144a3cb3",
                    "pid": null,
                    "pvalue": null,
                    "name": "Type",
                    "type": "RADIO",
                    "value": "Sedan",
                    "alias": null,
                    "isLeaf": true
                },
                {
                    "id": "0669d8b1-f175-4f46-a8d2-cea7bf9dc1e2",
                    "pid": null,
                    "pvalue": null,
                    "name": "Motor",
                    "type": "MULTI_SELECTION",
                    "value": ["Gas", "Electric"],
                    "alias": null,
                    "isLeaf": true
                }
            ],
            
            // Confidence value. It is only available when using model prediction.
            "modelConfidence": 0.83232,
            // Using model to predict the class. It is only available when using model prediction.
            "modelClass": "Person",
            
            // The coordinate information of the result varies according to the specific tool type.
            "contour": {
                "points": [],
                "pointN": 3057,
                "size3D": { "x": 2.2125, "y": 4.993, "z": 1.38 },
                "center3D": { "x": 3.9220652257399284, "y": -6.013346632547687, "z": 0.39 },
                "rotation3D": { "x": 0, "y": 0, "z": -1.6622375116055483 }
            },
                        
            // Meta info. Only for internal storage. Not required for import/export
            "meta": {
                // Annotation type
                // 3D_LABEL (3D cuboid)，2D_LABEL (2D b-box)，3D_SEGMENT，2D_SEGMENT
                "annotateType": "3D_LABEL",
                "classType":"",
                // "valid": true,
                // "checked": false,
                // "isProjection": false,
                // "invisibleFlag": false,
                // "resultType": "Dynamic",
                // "attrs": { "color": "#123" },
                // "resultStatus": "True_value",
                // "isStandard": false,
            }
        },
        
        // 2D bounding box
        {
            "id": "62383691-8077-44c2-ad8a-a6a7f54390c5",
            "type": "2D_BOX",
            "annotateType": "2D_LABEL",
            "version": "1",
            "createdBy": 1,
            "createdAt": "2012-03-29T10:05:45Z",
            
            "trackId": "c0627d18-1aa1-4788-ac88-09e8772ed9bb",
            "trackName": "Car 1",

            "classId": 1,
            "className": "",
            "classValues": {},

            "contour": {
                "points": [
                    { "x": 976.6271156786534, "y": 509.30442784738 },
                    { "x": 976.9704479066531, "y": 518.6737077997769 }
                ],
                "viewIndex": 3
            },
            
            "meta": {}
        },
        
        // 3D Segmentation
        {
            "id": "0d2c92c4-e96d-4672-abc7-a3480f412753",
            "type": "3D_SEGMENT_POINTS",
            "annotateType": "3D_SEGMENT",
            "version": "1",
            "createdBy": 1,
            "createdAt": "2012-03-29T10:05:45Z",
            
            "trackId": "c0627d18-1aa1-4788-ac88-09e8772ed9bb",
            "trackName": "Car 1",

            "classId": 1,
            "className": "",
            "classValues": {},

            "contour": {
                // Point cloud segmentation has a large amount of data, which is stored in files and is only used for internal storage
                "url": "https://basicai-prod-app-annotation.s3.us-west-2.amazonaws.com/tenant-1/dataset-1/data-flow/data-2/segment-points-0d2c92c4-e96d-4672-abc7-a3480f412753.json"
                // It is used for import/export. Due to the large amount of point information data, it is recommended to divide the JSON file by Data when exporting the annotation results of the dataset.
                "points": []
            },
            
            "meta": {}
        }
    ]
}
```
