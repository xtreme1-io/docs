# POST Delete Dataset

### POST Delete Dataset

POST /dataset/delete/{id}

#### Params

| Name | Location | Type   | Required | Description |
| ---- | -------- | ------ | -------- | ----------- |
| id   | path     | string | yes      | Dataset ID  |

> Response Examples

> Successful

```json
{
  "code": "OK",
  "message": "",
  "data": null
}
```

#### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | Successful  | Inline      |

#### Responses Data Schema

## Data Schema

### API result <a href="#tocs_api-result" id="tocs_api-result"></a>

```json
{
  "code": "string",
  "message": "string",
  "data": "string"
}

```

#### Attribute

| Name    | Type   | Required | Restrictions | Title             | Description |
| ------- | ------ | -------- | ------------ | ----------------- | ----------- |
| code    | string | true     | none         | Error code        | none        |
| message | string | true     | none         | Error description | none        |
| data    | string | true     | none         | none              |             |
