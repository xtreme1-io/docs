# Classification

The Classification contains only one attribute, but attributes can be nested in multiple layers. That is, the Option can also contain attributes.



<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption><p>The classification structure example</p></figcaption></figure>

{% code lineNumbers="true" %}
```json
JSON Example
{
    "id": 1,
    "attribute": {
        // ID
        "id": "64a16626-153f-4136-b7b4-572c10db08c3",
        // name
        "name": "Make",
        // type
        // RADIO，DROPDOWN，TEXT，MULTI_SELECTION
        "type": "RADIO",
        // Required
        "isRequired": true,
        // Option
        "options": [
            {
                "id": "92f6b36c-0589-4310-bdc9-5b6918a9a2be",
                "name": "Mercedes-Benz",
                "attributes": [
                    {
                        "id": "0fcb5add-4d2a-4d15-85e7-a8db966e6178",
                        "name": "Model",
                        "type": "RADIO",
                        "isRequired": false,
                        "options": [
                            {
                                "id": "b21e87ad-e096-44ba-a8aa-5adf7e7f5e10",
                                "name": "C300",
                                "attributes": [
                                    {
                                        "id": "69607032-9b53-4c95-90a8-6e378c19aa08",
                                        "name": "Color",
                                        "type": "RADIO",
                                        "isRequired": false,
                                        "options": [
                                            {
                                                "id": "beb371c0-5cda-4738-987c-9b9022a4b2d4",
                                                "name": "Black"
                                            },
                                            {
                                                "id": "d819cf06-ef0c-4e01-b787-8c89cfbf8578",
                                                "name": "White"
                                            }
                                        ]
                                    }
                                ]
                            },
                            {
                                "id": "6798d905-9532-4ba0-bc1f-81bdb849e165",
                                "name": "GLE450",
                                "attributes": [
                                    {
                                        "id": "37d18428-b2e7-4fa0-93ce-9033497df1ec",
                                        "name": "Color",
                                        "type": "RADIO",
                                        "isRequired": false,
                                        "options": [
                                            {
                                                "id": "6d007c39-d7cd-461a-9a07-1253718ae9cc",
                                                "name": "Black"
                                            },
                                            {
                                                "id": "6e6533bf-e194-4294-be0e-941f09a00f9a",
                                                "name": "Red"
                                            }
                                        ]
                                    }
                                ]
                            }
                        ]
                    },
                    {
                        "id": "24ce829b-9b60-4b88-99f7-379b144a3cb3",
                        "name": "Type",
                        "type": "RADIO",
                        "isRequired": false,
                        "options": [
                            {
                                "id": "9dbdbe60-9a95-4f6f-9a4e-6bf84efb8382",
                                "name": "Sedan"
                            },
                            {
                                "id": "e4497a0f-5c66-40a3-bce7-d9abc59ebbb3",
                                "name": "SUV"
                            }
                        ]
                    },
                    {
                        "id": "0669d8b1-f175-4f46-a8d2-cea7bf9dc1e2",
                        "name": "Motor",
                        "type": "MULTI_SELECTION",
                        "isRequired": false,
                        "options": [
                            {
                                "id": "14c9b60d-b4cb-475d-9cad-6dc8be58d67b",
                                "name": "Gas",
                                "attributes": [
                                    {
                                        "id": "9c0d296f-7141-4fd9-9cbe-c3d96a93d411",
                                        "name": "Engine Capacity",
                                        "type": "RADIO",
                                        "isRequired": false,
                                        "options": [
                                            {
                                                "id": "bd290f13-5c04-4828-bf2c-2ccfbca31ef3",
                                                "name": "1.0L"
                                            },
                                            {
                                                "id": "4858b7e1-c86c-40a9-96cf-7d1c2aa6ec77",
                                                "name": "1.5L"
                                            },
                                            {
                                                "id": "973100cc-ae0a-4379-995f-a98fcf0c4944",
                                                "name": "2.0L"
                                            }
                                        ]
                                    }
                                ]
                            },
                            {
                                "id": "65f62053-e37a-42cf-98a4-b6e87e8b27a5",
                                "name": "Diesel"
                            },
                            {
                                "id": "98b033e7-6c1c-4ade-95d5-684a5e6a26e0",
                                "name": "Electric",
                                "attributes": [
                                    {
                                        "id": "8e790d10-9931-43f6-82bb-60619f1a25ea",
                                        "name": "Capacity",
                                        "type": "RADIO",
                                        "isRequired": false,
                                        "options": [
                                            {
                                                "id": "ea9080e5-ce3b-4df8-a55e-b4f53a1f1213",
                                                "name": "<20kWh"
                                            },
                                            {
                                                "id": "fec71b3d-a7db-4d6c-a68a-d9c66ec49c6e",
                                                "name": "20~50kWh"
                                            },
                                            {
                                                "id": "d995f663-766b-403c-bfef-ee6aa1ae0379",
                                                "name": "50~100kWh"
                                            },
                                            {
                                                "id": "7f90dbcd-f81e-4638-b342-4dad454bf728",
                                                "name": ">=100kWh"
                                            }
                                        ]
                                    }
                                ]
                            }
                        ]
                    }
                ]
            },
            {
                "id": "f7192a9a-ecee-4eb3-825c-5007c47c1c86",
                "name": "BMW"
            }
```
{% endcode %}



