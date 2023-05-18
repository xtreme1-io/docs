---
description: Class and Classification
---

# Data Annotation Result

## Class

Class contains multiple attributes. Currently, it does not support multi-layer nesting of attributes.

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

## Classification <a href="#classification" id="classification"></a>

The Classification contains only one attribute, but attributes can be nested in multiple layers. That is, the Option can also contain attributes.

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

## Export Result Description <a href="#export-result-description" id="export-result-description"></a>

Please refer to[ Upload Dataset](../product-guides/upload-dataset.md) page for uploading pre-annotation result format and document structure.

### Description of Lidar-camera Fusion Annotation Results[#](https://docs.basic.ai/export\_class#description-of-lidar-camera-fusion-annotation-results) <a href="#description-of-lidar-camera-fusion-annotation-results" id="description-of-lidar-camera-fusion-annotation-results"></a>

```
[
  {
    "version": "Xtreme1 V0.6",
    "dataId": 3091870,
    "sourceName": "Ground Truth",
    "classificationValues": null,
    "objects": [
      {
        "id": "033DA6D7-3F4F-411E-B97C-DCD43C762BD4",
        "type": "3D_BOX",
        "classId": 455555556457,
        "className": "car",
        "trackId": "-COOq29Lf0S8XAvD",
        "trackName": "2",
        "classValues": [
          {
            "id": "7722689b-05a9-46b4-8e15-63dd0da55082",
            "name": "type",
            "type": "RADIO",
            "alias": "type",
            "value": "suv",
            "isLeaf": true
          }
        ],
        "contour": {
          "pointN": 1606,
          "points": [],
          "size3D": {
            "x": 4.784937233663604,
            "y": 3.0378181156906283,
            "z": 1.58
          },
          "center3D": {
            "x": -3.4826021259294277,
            "y": -9.45454056815398,
            "z": 0.56
          },
          "viewIndex": 0,
          "rotation3D": {
            "x": 0,
            "y": 0,
            "z": 0.5879414415603956
          }
        },
        "modelConfidence": null,
        "modelClass": ""
      },
      {
        "id": "7F88DC7C-4248-4B60-818A-291C387F2DE0",
        "type": "2D_BOX",
        "classId": 455555556457,
        "className": "car",
        "trackId": "-COOq29Lf0S8XAvD",
        "trackName": "2",
        "classValues": [],
        "contour": {
          "pointN": 0,
          "points": [
            {
              "x": 319.40950163247703,
              "y": 506.0158418379105
            },
            {
              "x": 314.60949113429047,
              "y": 662.7868372938835
            },
            {
              "x": 585.4095102457297,
              "y": 687.561499190987
            },
            {
              "x": 591.1197588821177,
              "y": 518.5722902765182
            },
            {
              "x": 582.1888667302327,
              "y": 505.75545447656134
            },
            {
              "x": 578.6576787082304,
              "y": 610.5962127027935
            },
            {
              "x": 768.6306027864321,
              "y": 624.0894977081099
            },
            {
              "x": 772.5861220555981,
              "y": 513.9219251252006
            }
          ],
          "size3D": {
            "x": 0,
            "y": 0,
            "z": 0
          },
          "center3D": {
            "x": 0,
            "y": 0,
            "z": 0
          },
          "viewIndex": 0,
          "rotation3D": {
            "x": 0,
            "y": 0,
            "z": 0
          }
        },
        "modelConfidence": null,
        "modelClass": ""
      },
      {
        "id": "6E1A62B0-A064-4A27-944B-B03DE6EA0B69",
        "type": "2D_RECT",
        "classId": 455555556457,
        "className": "car",
        "trackId": "-COOq29Lf0S8XAvD",
        "trackName": "2",
        "classValues": [],
        "contour": {
          "pointN": 0,
          "points": [
            {
              "x": 314.60949113429047,
              "y": 505.7554544765612
            },
            {
              "x": 314.60949113429047,
              "y": 687.561499190987
            },
            {
              "x": 772.5861220555983,
              "y": 687.561499190987
            },
            {
              "x": 772.5861220555983,
              "y": 505.7554544765612
            }
          ],
          "size3D": {
            "x": 0,
            "y": 0,
            "z": 0
          },
          "center3D": {
            "x": 0,
            "y": 0,
            "z": 0
          },
          "viewIndex": 0,
          "rotation3D": {
            "x": 0,
            "y": 0,
            "z": 0
          }
        },
        "modelConfidence": null,
        "modelClass": ""
      }
    ]
  }
]
```

### Description of Image Annotation Results <a href="#description-of-image-fusion-annotation-results" id="description-of-image-fusion-annotation-results"></a>

The coordinate origin is the upper left corner of the image.

```json
[
    {
        "version": "1.0",
        "dataId": 8171960,
        "sourceId": 384,
        "sourceType": "DATA_FLOW",          //Annotation type
        "sourceName": "Without Task",
        "validity": "VALID",
        "classificationValues": [           //Classification
            {
                "id": "321628",
                "values": [
                    {
                        "alias": "day",
                        "id": 321628,
                        "isLeaf": true,
                        "name": "day",
                        "value": "raining"
                    }
                ]
            },
            {
                "id": "321629",
                "values": []
            }
        ],
        "objects": [
            {
                "id": "4b9e7a69-21df-4d54-8e82-2fe60ca3ecd7",
                "type": "BOUNDING_BOX",     //Annotation type: bounding box
                "trackId": "mfNF5NoTMoQlzIpK",
                "trackName": "1",
                "classValues": [
                    {
                        "alias": "",
                        "id": "e26b9b9d-ce02-405c-972a-60508e5767c4",
                        "isLeaf": true,
                        "name": "color",     //Attributes
                        "value": "red"
                    },
                    {
                        "alias": "",
                        "id": "8b991d9b-43a4-4bbd-9e64-62dcfadd723b",
                        "isLeaf": true,
                        "name": "condition",
                        "value": "static"
                    }
                ],
                "contour": {
                    "points": [             //B-box coordinate
                        {
                            "x": 896.5871559633028,
                            "y": 501.2477064220182
                        },
                        {
                            "x": 1041.0275229357799,
                            "y": 650.9724770642201
                        }
                    ]
                },
                "modelConfidence": null,
                "modelClass": null,
                "className": "car"          //Label name
            }
        ],
        "segments": null,                   //Segmentation result
        "segmentPointsFileUrls": null
    }
]

```

