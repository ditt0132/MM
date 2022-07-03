Furniture Options
===========

Just like with Mobs, Furniture can have options to customize how they behave and can be placed.

```yml
TestFurniture:
  Id: IRON_NUGGET
  Display: 'Probably a Chair'
  Model:
  Type: FURNITURE
  Furniture:
    Material: 
    Model:
    Placement:
    Health:
    Barriers:
    Lights:
    Seats:
```

**Material: \[Item Material\]**

      * The vanilla item to represent the furniture WHEN PLACED!
      * This is not the same as Id in the item's base config, which will define how it looks in the inventory, or when placed in an item frame.

**Model: \[CustomModelData#\]**

      * The Model under Display represents the Model held IN HAND!
      * The Custom Model Data # the one below furniture is used to represent the furniture WHEN PLACED!
      * This is not the same as model in the item's base config, which will define how it looks in the inventory, or when placed in an item frame.

**Placement: \[FLOOR/HANGING/CEILING/WALL\]**

      * The way the furniture is meant to be placed.
      * FLOOR - the item is to be placed like a block, on the ground or off the side face of a block.
      * HANGING - the item is to be placed like an item frame or painting, against a wall
      * CEILING - the item is to be placed like glow berries, from a ceiling
      * WALL - similar to hanging, except the item orientation (the invisible frame) is in the same orientation as FLOOR (on the bottom face of the block, facing up)

      * defaults to FLOOR

**Health: \[number\]**

      * How many times the frame or barrier will need clicked before "breaking."

**Barriers: \[value\]**

      * The placement of barriers to make up the "hitbox" of the furniture.
      * format is in relation to the itemframe of the model.
      * light and barriers cannot share the same coordinate, and the furniture cannot be placed in a way that overlaps anything besides air. this includes rotating the furniture.

```yml
Barriers:
  - 0,0,0 #will place a barrier at the same block as the frame
  - 0,1,0 #will place a barrier above the frame by 1 block

```

**Lights: \[value\]**

      * The placement of light source blocks to make up the "light source" of the furniture.
      * format is in relation to the itemframe of the model.
      * light and barriers cannot share the same coordinate, and the furniture cannot be placed in a way that overlaps anything besides air. this includes rotating the furniture.

```yml
Lights:
  - 0,0,0 15 #will place a light block at the same block as the frame with a light level of 15
  - 0,1,0 10 #will place a light block above the frame by 1 block with a light level of 10
```

**Seats: \[value\]**

      * The placement of seat mount points to make up the "seating positions" of the furniture.
      * format is in relation to the itemframe of the model.
      * seats can overlap light and barriers.

```yml
Seats:
- 0,1,0,180,0 #will place a seat one block above the frame with a rotation clip of 180 degrees
```