# Contract level buyer information

The core OCDS schema provides space for a single `buyer` to be described for each contracting process. The buyer is defined as the organizations whose funds are directly used for the purchase of the goods, works or services described in the contract.

However, some forms of contracting process, such as framework agreements, may result in multiple contracts, with each contract signed by a different buyer. This extension adds a `contracts.buyer` object to support this scenario.

## Example

```json
{
  "contracts": [
    {
      "id": "1",
      "awardID": "1",
      "buyer": {
        "name": "Example Department of Transport",
        "id": "GB-GOV-00000000"
      }
    },
    {
      "id": "2",
      "awardID": "2",
      "buyer": {
        "name": "Example Department of Education",
        "id": "GB-GOV-12345678"
      }
    }
  ]
}
```

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.
