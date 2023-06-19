# Multiple buyers information

The core OCDS schema provides space for a single `buyer` to be described for each contracting process. The buyer is defined as the organization whose budget will be used for the purchase of the goods, services or works described in the contract.

However, some forms of contracting process, such as framework agreements, may result in multiple awards or contracts with a different buyer or buyers for each. This extension adds `awards.buyers` and `contracts.buyer` objects to support these scenarios.

## Legal Context

In the European Union, this extension's fields correspond to [eForms OPT-300-Contract-Signatory](https://docs.ted.europa.eu/eforms/latest/reference/business-terms/). See [OCDS for eForms](https://standard.open-contracting.org/profiles/eforms/latest/en/) for correspondences to eForms fields.

## Example

### Contracts

Two contracts are issued with a different buyer for each.

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

### Awards

One award is issued with two buyers.

```json
{
  "awards": [
    {
      "id": "1",
      "buyers": [
        {
          "name": "Example Department of Education",
          "id": "GB-GOV-12345678"
        },
        {
          "name": "Example Department of Transport",
          "id": "GB-GOV-00000000"
        }
      ]
    }
  ]
}
```

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.

## Changelog

### 2023-04-12

* Add `awards.buyers` object
