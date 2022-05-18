Furniture
---------
Crucible allows people to create "furniture", custom objects that can be placed in the world. These custom objects can be interacted with in different ways, and can also utilize skills!

Items that are configured to be furniture will have their corresponding furniture object placed in the world where the player is looking when right-clicked, and will drop the original item when broken by default (unless configured otherwise).

Furniture objects are rendered using custom modeled objects placed in either Item Frames or Armor Stands.

Furniture Options
-----------------
All options are placed under a "Furniture" section on an item.

### Base Options
- `Material` - The material of the furniture object.
- `Model` - The CustomModelData ID of the furniture object.
- `Health` - How many times a piece of furniture has to be punched within a short interval to break.

### Extra Blocks
Furniture can be configured with several special extras that are placed in the world along with it:
- Barrier Blocks
- Light Blocks (with light level)
- Seats (the closest seat is chosen when a player right-clicks the furniture)

Extra blocks are configured from the perspective of an object placed when the player is facing **yaw = 0**, and are rotated accordingly depending on how the furniture is placed.

Example Configuration
---------------------
```
TestFurniture:
  Id: IRON_NUGGET
  Display: 'Probably a Chair'
  Type: FURNITURE
  Furniture:
    Material: GOLD_NUGGET
    Model: 5
    Health: 3
    Barriers:
    - 0,0,0
    Lights:
    - 0,2,0 15
    Seats:
    - 0,0.9,0,0,0
  FurnitureSkills:
  - sound{s=entity.chicken.egg} @self ~onBlockPlace
  - sound{s=entity.chicken.egg} @self ~onInteract
  - sound{s=entity.zombie.break_wooden_door} @self ~onBlockBreak
  - sound{s=block.lever.click} @self ~onBlockRotate
  - sound{s=entity.zombie.attack_wooden_door} @self ~onDamaged
```