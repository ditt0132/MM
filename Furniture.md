Furniture
---------
Crucible allows people to create "furniture", custom objects that can be placed in the world. These custom objects can be interacted with in different ways, and can also utilize skills!

Items that are configured to be furniture will have their corresponding furniture object placed in the world where the player is looking when right-clicked, and will drop the original item when broken by default (unless configured otherwise).

Furniture objects are rendered using custom modeled objects placed in either Item Frames or Armor Stands.

Furniture Options
-----------------
All options are placed under a "Furniture" section on an item.

### Base Options
- `Type` - Defaults to `DISPLAY` on 1.19.4+, or `ITEM_FRAME` on lower versions.
- `Material` - The material of the furniture object.
- `Model` - The CustomModelData ID of the furniture object.
- `Health` - How many times a piece of furniture has to be punched within a short interval to break.
- `CanRotate` - If the furniture can be rotated. Defaults to true.
- `GlowingItem` - Whether the item should glow
- `Color` - A hex code to color the furniture. Only works on colorable items.

### Drops
Furniture drops are defined under the furniture `Drops` section. This uses the standard MythicMobs drop table format.

By default the furniture will drop itself when broken if there is no Drops field defined. You can make the furniture drop nothing by setting `Drops: []` or `DropSelf: false`

Type-Specific Options
---------------------

### DISPLAY
- `Height` - The height of the display entity used for rendering. Defaults to 1.
- `Width` - The width of the display entity used for rendering. Defaults to 1.
- `Billboard` - `FIXED`, `CENTER`, `HORIZONRAL`, `VERTICAL`
- `Brightness` - How bright the object is. Defaults to max.
- `InterpolationDelay` - The interpolation delay when the model changes.
- `InterpolationDuration` - The duration over which the model changes (useful for state changes)
- `Transform` - How the item is rendered. Defaults to `FIXED` which matches item frame rendering. Can also be `GROUND`, `GUI`, `HEAD`, `FIRSTPERSON_LEFTHAND`, `FIRSTPERSON_RIGHTHAND`, `THIRDPERSON_LEFTHAND`, `THIRDPERSON_RIGHTHAND`
- `Scale` - Changes the scaling sizes of the displayed item. Defaults to `.5,.5,.5` which matches item frame rendering. 

### ITEM_FRAME
- `GlowingFrame` - Whether the frame should be a glowing frame which renders the furniture at 100% brightness at all times. Defaults to false.


Extra Parts
-----------
Furniture can be configured with several special extras that are placed in the world along with it:

#### Barrier Blocks (in a `Barriers` list)
    Barriers:
    - 0,0,0

#### Light Blocks (with light level)
    Lights:
    - 0,2,0 15

#### Seats (the closest seat is chosen when a player right-clicks the furniture)
    Seats:
    - 0,0.9,0,0,0

Extra blocks are configured from the perspective of an object placed when the player is facing **yaw = 0**, and are rotated accordingly depending on how the furniture is placed.

Furniture States
----------------
Furniture States are other states that furniture can be swapped into using the `furnitureState` mechanic. 

This allows you to create dynamic furniture, such as:
- Crops that grow 
- A lamp that turns on or off
- Drawers that open and close

States are placed under a `States` section like so:
```
  TestFurniture:
    Furniture:
      Model: 1
      DefaultState: <name>
      States:
        <name_2>:
          Model: 2
        <name_3>:
          Model: 3
```
Each state can use any of the regular furniture options, and also `Lights: false` to turn light blocks off. When the `furnitureState` mechanic is called, the furniture will morph into the given state.

The `DefaultState` (defaults to "DEFAULT") allows you to set the name of the base version of the furniture for referencing in mecahnics.

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