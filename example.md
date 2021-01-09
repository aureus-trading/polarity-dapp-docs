# Example of the pSpec for Polarity LEND/AAVE Swap

1. Write the spec to match the application
```
{
   "name": "LEND/AAVE SWAP",
    "description":"This DApp swaps TN LEND to TN AAVE mirroring Ethereum based token swap ratio (100LEND:1AAVE)",
    "version": 1,
    "featuredImage":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAZAAAAGQCAMAAAC3Ycb+AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAMAUExURUxpcQDF0wDB0wC91QC11QC51QCz1f///wCx1QC90wC/0wCv1QDD0wC31QC71QCv0wC10wC509Tv+gCx0/r9/u35/KPg7T6+283n8ADB1ACz079qrqvg68fr9d3z+Cm72dXg7W/R5HLR4mDL4RC31z/E0SzB2pPb6F7T4pTd6eDV537U5VDH3zzG3FLO32PJ2lfH1sfr9NrA297E3rnn8MyVxNOjzLXk72bG2nSoyHmdwS3A2aKAt0zF3Qi81xm410xpccF3traVwsDJ3lu6z5uZwyPG2He90rB4tFnE3tS414uuzK3i6s6nzoPR375xs7SVw73q83/E22u+1Qq414jD2YTK2jrC2wDC0cWaxr59uFG6zqyiyM6HvqPF2QfE",
    "functions": [
        {
            "name":"swap",
            "requiredInputs": [
                {
                    "description": "",
                    "type":"payment",
                    "assetId": "3aasJh18EVT24wNEMybuY2a7E44ToM1QbgCeF9rVUgja"
                }
            ],
            "optionalInputs": [
            ]
        }
    ]
}
```

2. Base64 encode the specification and append 'base64:'

3. Send the information to your smart contract with the key "pspec" as apart of a [data transaction](https://docs.waves.tech/en/blockchain/transaction-type/data-transaction).

```
{
    "data": [
      {
        "type": "binary",
        "value": "base64:ewogICAgIm5hbWUiOiAiTEVORC9BQVZFIFNXQVAiLAogICAgImRlc2NyaXB0aW9uIjoiVGhpcyBEQXBwIHN3YXBzIFROIExFTkQgdG8gVE4gQUFWRSBtaXJyb3JpbmcgRXRoZX...",
        "key": "pspec"
      }
    ],
    "fee": 52000000,
    "type": 12,
    "version": 2
  }
  ```