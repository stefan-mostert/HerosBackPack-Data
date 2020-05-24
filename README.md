# Hero's BackPack-Data

The json on this site is consumed by the main Hero's Backpack site to provide reference data for items and bags.

## Contributing

If you want to contribute to the data, either because you have found something that is wrong or missing create a pull request and once merged the data hosted here will automatically flow through to Hero's Backpack for use by everyone.

## Format

all files has to be valid json

### Bags

```json
[
  {
    "gameSystemId": string,
    "name": string,
    "contentIsWorn": boolean,
    "isPlanarStorage": boolean,
    "weight": number,
    "maxCarryWeight": number,
    "maxItemLimit": number,
    "weightReduction": number
  }
]
```

| Property        | Type    | Description                                                                     |
| :-------------- | :------ | :------------------------------------------------------------------------------ |
| gameSystemId    | string  | Id to uniquely identify the game system.                                        |
| name            | string  | Name of the bag.                                                                |
| contentIsWorn   | boolean | Indicated if the content of this bag is being worn.                             |
| isPlanarStorage | boolean | Indicated if this bag is a planar storage bag like a 'Bag of Holding'.          |
| weight          | number  | This should always be a number and idicates the weight of the bag.              |
| maxCarryWeight  | number  | The maximum weight that this bag can hold. 0 for unlimited.                     |
| maxItemLimit    | number  | The maximum number of items that can be contained in this bag. 0 for unlimited. |
| weightReduction | number  | The amount of weight of the items i nside that is reduced by the bag.           |

### Items

```json
[
  {
    "gameSystemId": string,
    "name": string,
    "description": string,
    "source": string,
    "value": number,
    "weight": number,
    "tags": [string]
  }
]
```

| Property     | Type             | Description                                                                                   |
| :----------- | :--------------- | :-------------------------------------------------------------------------------------------- |
| gameSystemId | string           | Id to uniquely identify the game system.                                                      |
| name         | boolean          | Name of the item.                                                                             |
| description  | string           | Item description.                                                                             |
| value        | number           | Value of the item in the base currecy. (see [Value\*](#value))                                |
| weight       | number           | This should always be a number and idicates the weight of the item. (see [Weight\*](#weight)) |
| tags         | array of strings | array of tags associated with the item. Keep this to a minimum where possible.                |

### Value

Values are kept in a base currency.

| System | Base Currency |
| :----- | :------------ |
| PF1    | Silver        |
| PF2    | Silver        |

### Weight

Weight calculations will be done on items based on the assumed weight for that system. As a result weight on items should be entered in the base value of the system as inducated in the table below

| System | Weight System                                                                             |
| :----- | :---------------------------------------------------------------------------------------- |
| PF1    | Pounds (lb). Items in ounces should be entered as fractions                               |
| PF2    | Bulk. Items of light bulk should be entered as fractions (example 0.1 for one light bulk) |
