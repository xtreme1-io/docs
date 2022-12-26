---
description: >-
  ## GET Query the processing progress of the compressed dataset  GET
  /data/findUploadRecordBySerialNumbers  ### Params 
  |Name|Location|Type|Required|Title|Description| |---|---|---|---|---|---|
  |serial
---

# GET Query the data under the dataset



> Response Examples

> 200 Response

```json
{
  "code": "string",
  "message": "string",
  "data": [
    {
      "id": "string",
      "serialNumber": "string",
      "errorMessage": null,
      "totalFileSize": "string",
      "downloadedFileSize": "string",
      "totalDataNum": "string",
      "parsedDataNum": "string",
      "status": "string"
    }
  ]
}
```

#### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Successful  | Inline      |

#### Responses Data Schema

HTTP Status Code **200**

| Name                  | Type      | Required | Restrictions | Title                | description                                                               |
| --------------------- | --------- | -------- | ------------ | -------------------- | ------------------------------------------------------------------------- |
| » code                | string    | true     | none         | none                 |                                                                           |
| » message             | string    | true     | none         | none                 |                                                                           |
| » data                | \[object] | true     | none         | none                 |                                                                           |
| »» id                 | string    | false    | none         | none                 |                                                                           |
| »» serialNumber       | string    | false    | none         | Serial number        | none                                                                      |
| »» errorMessage       | null      | false    | none         | Error message        | none                                                                      |
| »» totalFileSize      | string    | false    | none         | File size            | none                                                                      |
| »» downloadedFileSize | string    | false    | none         | Downloaded file size | none                                                                      |
| »» totalDataNum       | string    | false    | none         | Total data size      | none                                                                      |
| »» parsedDataNum      | string    | false    | none         | Parsed data size     | none                                                                      |
| »» status             | string    | false    | none         | Status               | UNSTARTED,DOWNLOADING,DOWNLOAD\_COMPLETED,PARSING,PARSE\_COMPLETED,FAILED |

