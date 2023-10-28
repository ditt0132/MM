Brewing Recipes
-----------------

Brewing type recipes go inside a brewing stand. The Ingredient item goes in the top slot of the brewing stand with the InputItem going in one of the 3 bottom slots, the InputItem will be transformed into the Mythic Item.

## Configuration
```yaml
ExampleItem:
  Id: GOLD_NUGGET
  Model: 1
  Display: 'An example item'
  Recipes:
    BREWER_1:
      Type: BREWING
      Amount: 1
      Ingredient: apple
      InputItem: diamond
```