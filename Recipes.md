An item can have multiple recipes attached to it of any type, allowing items to be crafted in more than 1 way.

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

# Leftover Items
### Works only for `Shaped` and `Shapeless`

If you want to have items leftover inside the crafting grid after a recipe is completed you can add the`IngredientsLeftover` option. This will work in the same way crafting with a bucket of milk will leave the empty bucket in the grid. You can use any item including Mythic items. In the below example an empty bucket will be left in the crafting grid once the item is crafted.

```yaml
TestRecipe:
  Id: GOLD_NUGGET
  Display: 'Test Recipe Item'
  Recipes:
    SHAPELESS:
      Type: SHAPELESS
      Amount: 1
      IngredientsLeftover:
      - bucket
      Ingredients:
      - water_bucket
      - apple
```

# Conditions
### Works only for `Shaped` and `Shapeless`
You can check against a set of [Conditions](https://git.mythicmobs.io/mythiccraft/MythicMobs/-/wikis/Skills/conditions) that must be met in order for the player to be able to craft the item
```yaml
TestRecipe:
  Id: GOLD_NUGGET
  Display: 'Test Recipe'
  Recipes:
    NIGHT:
      Type: SHAPED
      Conditions:
      - night
      Ingredients:
      - FEATHER | AIR
      - AIR | FEATHER
```

# CraftSkills
### Works only for `Shaped` and `Shapeless`
Allows the player to execute a skill once the associated item is crafted.  
The `<skill.var.crafts>` placeholder can be used to fetch the amount of items crafted.  
```yaml
ThiccItem:
     Recipes:
       Recipe:
         Type: SHAPELESS
         Ingredients:
         - slime_ball
         - honey_bottle
         CraftSkills:
         - lightning @self
```


# Example Crafting Configuration
Here is an example of an item with multiple recipes attached to it.
```yaml
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