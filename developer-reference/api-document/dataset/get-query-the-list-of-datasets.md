# GET Query the list of datasets

### GET Query the list of datasets

GET /dataset/findByPage

#### Params

| Name            | Location | Type    | Required | Description                                   |
| --------------- | -------- | ------- | -------- | --------------------------------------------- |
| pageNo          | query    | integer | yes      | Current page number                           |
| pageSize        | query    | string  | yes      | Number of items displayed per page            |
| name            | query    | string  | no       | Name                                          |
| createStartTime | query    | string  | no       | Start time (Date type)                        |
| createEndTime   | query    | string  | no       | End time (Date type)                          |
| sortFiled       | query    | string  | no       | Sort field (NAME, CREATED\_AT, UPDATED\_AT)   |
| ascOrDesc       | query    | string  | no       | Ascending or descending (ASC,DESC)            |
| type            | query    | string  | no       | Data type: LIDAR\_FUSION, LIDAR\_BASIC, IMAGE |

> Response Examples

> 200 Response

```json
{
  "code": "string",
  "message": "string",
  "data": {
    "pageSize": 0,
    "pageNo": 0,
    "total": 0,
    "list": [
      {
        "id": 0,
        "name": "string",
        "type": "string",
        "description": null,
        "annotatedCount": 0,
        "notAnnotatedCount": 0,
        "invalidCount": 0,
        "itemCount": 0,
        "datas": [
          {
            "id": null,
            "datasetId": null,
            "name": null,
            "content": null,
            "status": null,
            "annotationStatus": null,
            "lockedBy": null
          }
        ]
      }
    ]
  }
}
```

#### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Successful  | Inline      |

#### Responses Data Schema

HTTP Status Code **20**
