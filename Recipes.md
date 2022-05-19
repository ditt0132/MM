Crafting Recipes
----------------
Added in v1.5.0 dev builds.

### Available Recipe Types
- `SHAPELESS` - A shapeless recipe
- `SHAPED` - A recipe that requires a certain shape
- `FURNACE` - In a Furnace
- `CAMPFIRE` - In a Campfire
- `BLASTING` - In a Blast Furnace
- `SMOKING` - In a Smoker
- `BREWING` - Brewed in a brewing stand

Example Configuration
---------------------
```
TestRecipe:
  Id: GOLD_NUGGET
  Model: 5
  Display: 'Test Recipe Item'
  Recipes:
    FURNACE:
      Type: FURNACE
      Amount: 1
      CookingTime: 120
      Experience: 5
      Ingredient: diamond
    SHAPED_1:
      Type: SHAPED
      Amount: 1
      Ingredients:
      - apple | air
      - air | apple
    SHAPELESS_1:
      Type: SHAPELESS
      Amount: 1
      Ingredients:
      - apple
      - apple
      - diamond
      - TestRecipe
```