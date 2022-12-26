# POST Edit Dataset

## Dataset

### POST Edit Dataset

POST /dataset/update/{id}

> Body Parameters

```json
{
  "ID": 0,
  "Name": "string",
  "Description ": "string"
}
```

#### Params

| Name          | Location | Type        | Required | Title       | Description |
| ------------- | -------- | ----------- | -------- | ----------- | ----------- |
| id            | path     | integer     | yes      | ID          |             |
| body          | body     | object      | no       | none        |             |
| » ID          | body     | integer     | yes      | ID          | none        |
| » Name        | body     | string      | yes      | Name        | none        |
| » Description | body     | string¦null | no       | Description | none        |

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

HTTP Status Code **200**

| Name      | Type   | Required | Restrictions | Title             | description |
| --------- | ------ | -------- | ------------ | ----------------- | ----------- |
| » code    | string | true     | none         | Error code        | none        |
| » message | string | true     | none         | Error description | none        |
| » data    | object | true     | none         | Data              | none        |

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
