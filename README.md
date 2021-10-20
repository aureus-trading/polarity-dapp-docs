# Polarity-Dapp-Docs

Polarity UI is able to dynamically generate the UI for a DApp based on a data-entry against a DApp with the name 'pspec'. The functionality serves to allow for interaction with DApps and lower the barrier of entry for participant in the ecosystem.

## Specifications v2.0
```
{
    "name": "",
    "description":"",
    "version": "",
    "featuredImage":"data:image/png;base64,<base 64 encoded image>"
    "functions": [
        {
            "name":"setup",
            "requiredInputs": [
                {
                    "type":"payment",
                    "assetId": "",
                    "fixedAmount":""
                },
                {
                    "type": "paymentRange",
                    "assetId": "", (optional)
                    "minPayments": 2,
                    "maxPayments": 4
                }
            ],
            "optionalInputs": [
                {
                    "type": "payment",
                    "assetId": "",
                    "fixedAmount": ""
                },
                {
                    "type": "paymentRange",
                    "assetId": "", (optional)
                    "minPayments": 1,
                    "maxPayments": 5
                }
            ],
            "showResult": true
        }
    ],
    "visibleDataFields": {
      "fieldName: { 
        "transform": ""
      }
    }
}
```

## Accepted Fields

### PSpec

|Field Name|Description|
|-|-|
|Name|The name to be used for the DApp|
|Description|A description that is placed under the title|
|Version|The version of the DApp intepreter to use (Default to 1)|
|Featured Image|The base64 encoded image which should include data:image/png;base64,\<encoded image\>. Featured images should be a maximum of 20KB as network data tx can have a maximum of 32,767 bytes value. https://docs.waves.tech/en/blockchain/transaction-type/data-transaction#json-representation|
|Functions|Field defining the UI behavior|
|visibleDataFields|Map of visible datafields to show as apart of the DApp UI|

## Accepted Subfields

### Function
|Name|Description|
|-|-|
|name|The name of the function to invoke i.e. swap|
|requiredInput|The required inputs to allow users to specify as apart of the UI, refer to subfield Inputs|
|optionalInputs|The optional inputs to allow users to specify as apart of the UI, refer to subfield Inputs|
|showResult|Whether or not to show the script result when run|


### Inputs (requiredInput | optionalInputs)
|Name|Description|
|-|-|
|description|The description to display to the user|
|type|The type of input that will be passed, as of version 2.0 [payment and paymentRange](https://docs.waves.tech/en/ride/v4/structures/common-structures/invocation) are supported|
|assetId|The asset id to filter the selectable assets on, optional in paymentRange, if not present will enable user to pick a single asset for all payments in that range|
|fixedAmount| This amount of the asset is required|
|minPayments| The minimum number of different payments in that range|
|maxPayments| The maximum number of different payments in that range|


### Return

The State change will show to users however if you want to show users a direct message you can include in your return a field with key "message"