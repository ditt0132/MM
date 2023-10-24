## Super and Mega Workbenches
You can make shaped recipes that takes up to a 6x6 grid in space, or shapeless ones that take up more than 9 items.    
To be able to use any such recipes, you will have to access the `super` or `mega` workbenches (via the use of the `/superworkbench <player>` and `/megaworkbench <player>` commands) whose size is, respectively, of `5x5` and `6x6`.  


| Workbench | Size | Command                   |
| --------- | ---- | ------------------------- |
| super     | 5x5  | `/superworkbench`, `/swb` |
| mega      | 6x6  | `/megaworkbench`, `/mwb`  |


## Integration
In order to integrate this tool into your server without the need for players to actually type the command, there is a simple method: **Use the command mechanic** from your custom mob/item/block/furniture.

```yaml
ExampleCraftingTable:
  Id: IRON_NUGGET
  Display: 'Mega Crafting Table'
  Type: FURNITURE
  Furniture:
    Material: GOLD_NUGGET
    Model: 5
    Health: 1
    Barriers:
    - 0,0,0
  FurnitureSkills:
  - command{c="megaworkbench <trigger.name>"} @trigger ~onInteract
```

## Examples
Example of a shaped recipe using a 6x6 crafting grid.
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