Crafting Recipes
----------------
Added in v1.5.0 dev builds.

### Available Recipe Types
- [`SHAPELESS`](Recipes/Shapeless) - A shapeless recipe
- [`SHAPED`](Recipes/Shaped) - A recipe that requires a certain shape
- [`FURNACE`](Recipes/Furnace) - In a Furnace
- [`CAMPFIRE`](Recipes/Furnace) - In a Campfire
- [`BLASTING`](Recipes/Furnace) - In a Blast Furnace
- [`SMOKING`](Recipes/Furnace) - In a Smoker
- [`STONECUTTING`](Recipes/Stonecutting) - In a stonecutter
- [`SMITHING`](Recipes/Smithing) - In a smithing table
- [`BREWING`](Recipes/Brewing) - Brewed in a brewing stand

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
    BREWER_1:
      Type: BREWING
      Amount: 1
      Ingredient: apple
      InputItem: diamond
    SHAPELESS_1:
      Type: SHAPELESS
      Amount: 1
      Ingredients:
      - apple
      - apple
      - diamond
      - TestRecipe
```