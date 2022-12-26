# POST Upload the dataset compressed package

### POST Upload the dataset compressed package

POST /data/upload

> Body Parameters

```json
{
  "fileUrl": "string",
  "datasetId": "string",
  "source": "string"
}
```

#### Params

| Name        | Location | Type   | Required | Title      | Description |
| ----------- | -------- | ------ | -------- | ---------- | ----------- |
| body        | body     | object | no       | none       |             |
| » fileUrl   | body     | string | yes      | File path  | none        |
| » datasetId | body     | string | yes      | Dataset ID | none        |
| » source    | body     | string | yes      | Source     | LOCAL, URL  |

> Response Examples

> 200 Response

```json
{
  "code": "string",
  "message": "string",
  "data": "string"
}
```

#### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Successful  | Inline      |

#### Responses Data Schema

HTTP Status Code **200**

| Name      | Type   | Required | Restrictions | Title         | description |
| --------- | ------ | -------- | ------------ | ------------- | ----------- |
| » code    | string | true     | none         | none          |             |
| » message | string | true     | none         | none          |             |
| » data    | string | true     | none         | Serial number | none        |

## Data Schema
