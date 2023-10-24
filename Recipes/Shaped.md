## Shaped Recipes
Shaped recipes require the items to be in a certain shape in the crafting table. Note that in vanilla mode, recipes are automatically mirrored.


## Super and Mega Workbenches
You can make recipes that takes up to a 6x6 grid in space.  
To be able to use any such recipe, you will have to access the `super` or `mega` workbenches (via the use of the `/superworkbench` and `/megaworkbench` commands) whose size is, respectively, of `5x5` and `6x6`.  


| Workbench | Size | Command                   |
| --------- | ---- | ------------------------- |
| super     | 5x5  | `/superworkbench`, `/swb` |
| mega      | 6x6  | `/megaworkbench`, `/mwb`  |


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