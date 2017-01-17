This extension exists to the stage the proposal in #382 to add a ```buyer``` property to the ```contract``` section.

This extension depends on the [v1.1 update to organization handling](https://github.com/open-contracting/ocds_extension_parties)

# Contract level buyer information

## Background

The ```buyer``` section of an OCDS release is used to reference the entry in the ```parties``` section with the organization details of the buyer for the contracting process.

A single ```buyer``` is specified for each contracting process and this buyer is associated with all contracts resulting from the contracting process.

## Providing information on buyers per contract

Some OCDS implementations include types of contracting process, for example framework agreements, which result in multiple contracts with each contract signed by a different buyer.

This extension provides a way to provide ```buyer``` information on a per contract basis.

## Extension fields

This extension adds a ```buyer``` property to the ```contract``` section of OCDS.

```contract.buyer``` is an ```organizationReference``` consisting of the following fields:

* ```name``` - The name of the party being referenced. This must match the name of an entry in the ```parties``` section.
* ```id``` - The id of the party being referenced. This must match the id of an entry in the ```parties``` section.

## Dependencies

This extension depends on the [v1.1 update to organization handling](https://github.com/open-contracting/ocds_extension_parties) which introduced the ```parties``` section and the ```organizationReference``` object.

## Example

```JSON
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
