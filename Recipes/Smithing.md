Smithing Recipes
-----------------
Smithing recipes allow you to create recipes in a smithing table. The BaseItem is the item that goes in the first slot with the Ingredient item being the item in the 2nd slot.
## Configuration
```yaml
ExampleItem:
  Id: DIAMOND
  Model: 1
  Display: 'Synthetic Diamond'
  Recipes:
    SMITHING_1:
      Type: SMITHING
      Amount: 1
      BaseItem: COAL
      Ingredient: COAL
```