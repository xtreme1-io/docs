# GET Query a single dataset

### GET Query a single dataset

GET /dataset/info/{id}

#### Params

| Name | Location | Type    | Required | Description |
| ---- | -------- | ------- | -------- | ----------- |
| id   | path     | integer | yes      | ID          |

> Response Examples

> Successful

```json
{
  "code": "OK",
  "message": "",
  "data": {
    "id": 750058,
    "name": "createBy_gh",
    "type": "LIDAR_FUSION",
    "description": null
  }
}
```

#### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Successful  | Inline      |

#### Responses Data Schema

HTTP Status Code **200**

| Name           | Type    | Required | Restrictions | Title        | description |
| -------------- | ------- | -------- | ------------ | ------------ | ----------- |
| » code         | string  | true     | none         | none         |             |
| » message      | string  | true     | none         | none         |             |
| » data         | object  | true     | none         | none         |             |
| »» id          | integer | true     | none         | Dataset ID   | none        |
| »» name        | string  | true     | none         | Dataset name | none        |
| »» type        | string  | true     | none         | Dataset type | none        |
| »» description | null    | true     | none         | Description  | none        |

