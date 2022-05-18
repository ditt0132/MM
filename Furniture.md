Furniture
---------
Crucible allows people to create "furniture", custom objects that can be placed in the world. These custom objects can be interacted with in different ways, and can also utilize skills!

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