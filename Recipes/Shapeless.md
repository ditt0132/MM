Shapeless Recipes
-----------------
A shapeless recipe is one where the order of the items doesn't matter, the items can be placed inside a crafting grid in any order.
## Configuration
```yaml
ExampleItem:
  Id: GOLD_NUGGET
  Model: 1
  Display: 'An example item'
  Recipes:
    SHAPELESS:
      Type: SHAPELESS
      Amount: 1
      Ingredients:
      - apple
      - apple
      - diamond
      - TestRecipe
```