## Shaped Recipes
Shaped recipes require the items to be in a certain shape in the crafting table. Note that in vanilla mode, recipes are automatically mirrored.


## Configuration
Example using a 2x2 crafting grid
```yaml
ExampleItem:
  Id: GOLD_NUGGET
  Model: 1
  Display: 'An example item'
  Recipes:
    SHAPED:
      Type: SHAPED
      Amount: 1
      Ingredients:
      - stone | apple
      - apple | stone 
```
##
Example using a 3x3 crafting grid.
```yaml
ExampleItem:
  Id: GOLD_NUGGET
  Model: 1
  Display: 'An example item'
  Recipes:
    SHAPED:
      Type: SHAPED
      Amount: 1
      Ingredients:
      - stone | apple | apple
      - apple | stone | apple
      - apple | apple | stone 
```
##
Example using a 6x6 crafting grid.
```yaml
ExampleItem:
  Id: GOLD_NUGGET
  Model: 1
  Display: 'An example item'
  Recipes:
    SHAPED:
      Type: SHAPED
      Amount: 1
      Ingredients:
      - AIR | AIR | AIR | AIR | AIR | STONE
      - AIR | AIR | AIR | AIR | STONE | AIR
      - AIR | AIR | AIR | STONE | AIR | AIR
      - AIR | AIR | STONE | AIR | AIR | AIR
      - AIR | STONE | AIR | AIR | AIR | AIR
      - STONE | AIR | AIR | AIR | AIR | AIR
```