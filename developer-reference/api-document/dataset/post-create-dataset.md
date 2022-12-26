# POST Create Dataset

## Dataset

### POST Create Dataset

POST /dataset/create

> Body Parameters

```json
{
  "name": "Test",
  "type": "IMAGE",
  "description": "This is a test again."
}
```

#### Params

| Name          | Location | Type   | Required | Title       | Description                        |
| ------------- | -------- | ------ | -------- | ----------- | ---------------------------------- |
| body          | body     | object | no       | none        |                                    |
| » name        | body     | string | yes      | Name        | none                               |
| » type        | body     | string | yes      | Type        | LIDAR\_FUSION, LIDAR\_BASIC, IMAGE |
| » description | body     | string | yes      | Description | none                               |

> Response Examples

> Successful

```json
{
  "code": "OK",
  "message": "",
  "data": {
    "id": 766400,
    "name": "Test name",
    "type": "IMAGE",
    "description": "This is a test"
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
| »» type        | string  | true     | none         | Type         | none        |
| »» description | string  | true     | none         | Discription  | none        |

