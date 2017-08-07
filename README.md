# Contract level buyer information

## Background

The core OCDS schema provides space for a single ```buyer``` to be described for each contracting process. The buyer is defined as the organisations whose funds are directly used for the purchase of the goods, works or services described in the contract.

However, some forms of contracting process, such as framework agreements, may result in multiple contracts, with each contract signed by a different buyer.

This extension provides a way to provide ```buyer``` information on a per contract basis.

## Extension fields

This extension adds a ```buyer``` property to the ```contract``` section of OCDS.

```contract.buyer``` is an ```organizationReference``` consisting of the following fields:

* ```name``` - The name of the party being referenced. This must match the name of an entry in the ```parties``` section.
* ```id``` - The id of the party being referenced. This must match the id of an entry in the ```parties``` section.

## Dependencies

This extension is only valid from OCDS Version 1.1, as it makes use of the updated organisation reference approach.

## Example

```json
"contracts": [
  {
    "id": "001",
    "buyer": {
      "name": "Example Department of Transport",
      "id": "GB-GOV-00000000"
    }
  },
  {
    "id": "002",
    "buyer": {
      "name": "Example Department of Education",
      "id": "GB-GOV-12345678"
    }
  }
]
```

## Todo

* Update documentation once the nomenclature of the parties extension is finalised.
