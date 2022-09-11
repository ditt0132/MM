Shaped Recipes
-----------------

Shaped recipes require the items to be in a certain shape in the crafting table. Note that in vanilla mode, recipes are automatically mirrored.

## Configuration
```
ExampleItem:
  Id: GOLD_NUGGET
  Model: 1
  Display: 'An example item'
  Recipes:
    SHAPED:
      Type: SHAPED
      Amount: 1
      Ingredients:
      - apple | apple
      - apple | apple
```