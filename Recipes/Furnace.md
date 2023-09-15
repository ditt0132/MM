Furnace Recipes
-----------------

"Furnace" type recipes, including FURNACE, BLASTING, CAMPFIRE, SMOKER, etc all use the same options, with the only difference being the type of workstation required.

## Configuration
```
ExampleItem:
  Id: GOLD_NUGGET
  Model: 1
  Display: 'An example item'
  Recipes:
    FURNACE:
      Type: FURNACE
      Amount: 1
      CookingTime: 400
      Ingredient: APPLE
    BLASTING:
      Type: BLASTING
      Amount: 1
      CookingTime: 200
      Ingredient: APPLE
```