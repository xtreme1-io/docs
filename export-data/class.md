# Class

Class contains multiple attributes. Currently, it does not support multi-layer nesting of attributes.

<figure><img src="../.gitbook/assets/image (1) (2).png" alt=""><figcaption><p>The class structure example</p></figcaption></figure>

```json
JSON Example
{
    // ID
    "id": 1,
    // Class name
    "name": "Car",
    // Result color
    "color": "#7dfaf2",
    // Annotation tool type
    // BOUNDING_BOX，CUBOID，POLYLINE
    "toolType": "CUBOID",
    // Tool options
    "toolOptions": {},
    // Attribute
    "attributes": [
        {
            "id": "bdc9acdf-4337-42de-8964-a1b5b6820287",
            "name": "Make",
            "type": "RADIO",
            "isRequired": true,
            "options": [
                {
                    "id": "92f6b36c-0589-4310-bdc9-5b6918a9a2be",
                    "name": "Mercedes-Benz"
                },
                {
                    "id": "f7192a9a-ecee-4eb3-825c-5007c47c1c86",
                    "name": "BMW"
                }
            ]
        },
        {
            "id": "0fcb5add-4d2a-4d15-85e7-a8db966e6178",
            "name": "Model",
            "type": "RADIO",
            "isRequired": true,
            "options": [
                {
                    "id": "b21e87ad-e096-44ba-a8aa-5adf7e7f5e10",
                    "name": "C300"
                },
                {
                    "id": "6798d905-9532-4ba0-bc1f-81bdb849e165",
                    "name": "GLE450"
                }
            ]
        },
        {
            "id": "24ce829b-9b60-4b88-99f7-379b144a3cb3",
            "name": "Type",
            "type": "RADIO",
            "isRequired": true,
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
            "name": "动力",
            "type": "MULTI_SELECTION",
            "isRequired": true,
            "options": [
                {
                    "id": "14c9b60d-b4cb-475d-9cad-6dc8be58d67b",
                    "name": "Gas"
                },
                {
                    "id": "65f62053-e37a-42cf-98a4-b6e87e8b27a5",
                    "name": "Diesel"
                },
                {
                    "id": "98b033e7-6c1c-4ade-95d5-684a5e6a26e0",
                    "name": "Electric"
                }
            ]
        }
    ]
}
```

