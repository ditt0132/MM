Stonecutting Recipes
-----------------

Stonecutting recipes show up in the Stonecutter. 

At this time the stonecutter is very basic, and only supports inputting vanilla blocks, and will allow you to put in custom items with the same material type. You should keep this in mind when designing recipes.

## Configuration
```
ExampleItem:
  Id: GOLD_NUGGET
  Model: 1
  Display: 'An example item'
  Recipes:
    STONECUTTING:
      Type: STONECUTTING
      Amount: 4
      BaseItem: GRASS_BLOCK
```