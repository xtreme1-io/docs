# 🎹 API Document

Xtreme1’s APIs can manage your datasets in Xtreme1, including uploading datasets and annotation, exporting results, and running model prediction, so that developers can integrate Xtreme1 with other products.

## Authentication&#x20;

The Xtreme1 open API adopts the popular Bearer Token authentication method.&#x20;

1. Generate a token on the API token management page;
2. Pass the token to the API server through the `Authorization` header when calling the API.

```bash
curl --location --request GET 'http://localhost:8190/api/dataset/info/1' \
--header 'Authorization: Bearer eyJhbGciOiJIUzUxMiJ9.eyJpc3MiOiJCYXNpY0FJIiwiaWF0IjoxNjcxMTczMjM4LCJzdWIiOiIxMDAzIn0.95afi8SSXWEfLwNw0ZPBvCUt_AJn3EoyBPkHcHvnJwWuOFLNyKQ_u-RluNth2r2ihVCliaMnBhGBfUph0wdLtQ'
```

{% hint style="info" %}
Some complex usage scenarios require a combination of calling multiple APIs to complete business operations.&#x20;
{% endhint %}

Here are some explanations so that developers can understand and use the APIs.

### Upload compressed dataset file

A dataset contains a large number of files (over 100 GB), and a single data may also contain multiple files. For example, a single Lidar\_fusion data contains a PCD file, one or more sets of camera images, and a JSON file of annotation results. These files need to somehow belong under the same data.&#x20;

If the traditional form file upload method is used, the request will be more complicated, and only a single data can be uploaded, which is very inefficient. A better way is to use compressed packages. The user can prepare a compressed package according to the specified directory structure, which contains multiple data (even the data of the entire data set). Considering that it will take a long time for the server to process the compressed package, this part of the work will be processed asynchronously in the background, and the caller can check whether the background processing is completed according to the serial number.

In addition, in order to improve performance, the compressed package is uploaded directly to the object storage service without going through the API service. The complete upload process is as follows:

1. Prepare the dataset compression package locally;
2. Call the "Generate file direct upload address" API to get a signed compressed package upload address and a compressed package access address;
3. According to the form file upload format (`Content-Type: multipart/form-data`), use the `PUT` method to request the upload address to directly upload the compressed package to the object storage service;
4. Call the "Upload Dataset Compressed Package" API to upload the compressed package to a certain dataset. At this time, you only need to provide the access address of the compressed package obtained earlier, and you will get a serial number of the background processing task;
5. Call the "Query Dataset Compression Package Processing Progress" API to query whether the background processing is complete.

Find the API Reference document at [here](https://www.apifox.cn/apidoc/shared-2f8468c3-a269-4e3d-9df7-c589bda69450).

