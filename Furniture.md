Crucible allows people to create "furniture", custom objects that can be placed in the world. These custom objects can be interacted with in different ways, and can also utilize skills!

Items that are configured to be furniture will have their corresponding furniture object placed in the world where the player is looking when right-clicked, and will drop the original item when broken by default (unless configured otherwise).

Furniture objects are rendered using custom modeled objects placed in either Item Frames or Armor Stands.

<!-- TABLE OF CONTENTS -->
<!-- I am perfectly aware of the [[_TOC_]] shortcut, but in this instance it is not ideal -->
- [Furniture Options](#furniture-options)
  - [Base Options](#base-options)
  - [Type-Specific Options](#type-specific-options)
- [Drops](#drops)
- [Furniture States](#furniture-states)
- [Examples](#examples)

## Furniture Options

All options are placed under a `Furniture` section on an item, like so:
```yaml
ExampleFurniture:
  Id: IRON_NUGGET
  Type: FURNITURE
  Model: 5
  Furniture:
    Material: GOLD_NUGGET
    Model: 6
```

##

### **Base Options**

#### Type
The type of the entity that will be used to display the Furniture's `Material`. Defaults to `DISPLAY` on 1.19.4+, or `ITEM_FRAME` on lower versions
```yaml
  Furniture:
    Type: DISPLAY
```

#### Material
The base material of the Furniture. If used on its own, the Furniture will only display this item as if it was placed in an Item Frame, but with the `Model` Option and an accompanying ResourcePack, custom models can be displayed
```yaml
  Furniture:
    Material: BRICK
```

#### Model
The CustomModelData value of the Furniture's `Material`
```yaml
  Furniture:
    Material: BRICK
    Model: 12
```

#### Health
The amount of times a piece of Furniture can be hit within a short timespan before breaking
<br>Defaults to `1`
```yaml
  Furniture:
    Health: 3
```

#### Hitbox
The dimension of the Interaction Entity that will make up the hitbox of the Furniture. The hitbox will not be solid or repel entities, but can be interacted with.
<br>Defaults to `1`x`1` if not barriers are present, or `0`x`0` if they are
```yaml
  Furniture:
    Hitbox:
      Height: 1
      Width: 1
```

#### CanRotate
If the Furniture can be rotated if right clicked while sneaking
<br>Defaults to `true`
```yaml
  Furniture:
    CanRotate: false
```

#### GlowingItem
If the Furniture should be glowing
<br>Defaults to `false`
```yaml
  Furniture:
    GlowingItem: true
```

#### DropSelf
If the Furniture should drop itself once broken
<br>Defaults to `true` in most cases and to `false` if some [`Drops`](#drops) have been specified
```yaml
  Furniture:
    DropSelf: false
```

#### Color
The RGB color for the furniture to use. Only works on colorable items
```yaml
  Furniture:
    Color: 44,224,223
```

#### Placement
Where the Furniture is meant to be placed:
  - `FLOOR` - The item is to be placed like a block, on the ground or off the side face of a block
  - `HANGING` - The item is to be placed like an item frame or painting, against a wall
  - `CEILING` - The item is to be placed like glow berries, from a ceiling
  - `WALL` - Similar to hanging, except the item orientation (the invisible frame) is in the same orientation as FLOOR (on the bottom face of the block, facing up)

Defaults to `FLOOR`
```yaml
  Furniture:
    Placement: FLOOR
```

#### Diagonalable
Whether or not furniture can be rotated at 45 degree angles instead of 90 degree angles. Defaults to false.
```yaml
  Furniture:
    Diagonalable: true
```

#### Barriers
A list of relative coordinates where barriers will be placed. Useful to make a solid hitbox for the Furniture. Can be used with the `Hitbox` Option, and if both are present then both the Hitbox and the Barrier will act as the Furniture's Hitbox
- The `x` is left/right
- The `y` is up/down
- The `z` is forward/backward
The barriers rotates with the Furniture, and a Furniture cannot be placed or rotated if doing so would overlaps one of its barriers with anything but air blocks.
```yaml
  Furniture:
    Barriers:
    - 0,0,0 # Will be placed on the same block as the base of the Furniture
    - 0,1,0 # Will be placed one block above the base of the Furniture
    - 0,0,1 # Will be placed one block "forward" the base of the Furniture, based on the Furniture's rotation 
```

#### Lights
A list of relative coordinates and an integer value that determines where the light sources will be placed and their light level. Useful to make the "light sources" of the Furniture
- The `x` is left/right
- The `y` is up/down
- The `z` is forward/backward
- The `INTEGER` value is for the light level of the light block
The light blocks rotates with the Furniture, and a Furniture cannot be placed or rotated if doing so would overlaps one of its light blocks with anything but air blocks.
A light block and a barrier **cannot be placed** on the same spot.
```yaml
  Furniture:
    Lights:
    - -1,0,0 15 # Will be placed one block "to the right" the base of the Furniture, based on the Furniture's rotation with light level 15.
    - 0,-1,0 15 # Will be placed one block below the base of the Furniture
    - 0,0,-1 15 # Will be placed one block "backward" the base of the Furniture, based on the Furniture's rotation 
```

#### Seats
A list of relative coordinates where the Seats of the Furniture will be placed. Players can use them by right clicking the Furniture.
- The `x` is left/right
- The `y` is up/down
- The `z` is forward/backward
A Seat can overlap barriers and light sources of the Furniture and every kind of block present in the world when rotated.
If multiple seats are created, when a player right clicks on a furniture the closest free spot, if any, will be selected as the seat
```yaml
  Furniture:
    Seats:
    - 0,1,0,0,0 # A seat will be placed on block above the base of the Furniture
```

##

### **Type-Specific Options**

#### Display
- `Height` - The height of the display entity used for rendering. Defaults to 1.
- `Width` - The width of the display entity used for rendering. Defaults to 1.
- `Billboard` - `FIXED`, `CENTER`, `HORIZONRAL`, `VERTICAL`
- `Brightness` - How bright the object is. Defaults to max.
- `InterpolationDelay` - The interpolation delay when the model changes.
- `InterpolationDuration` - The duration over which the model changes (useful for state changes)
- `Transform` - How the item is rendered. Defaults to `FIXED` which matches item frame rendering. Can also be `GROUND`, `GUI`, `HEAD`, `FIRSTPERSON_LEFTHAND`, `FIRSTPERSON_RIGHTHAND`, `THIRDPERSON_LEFTHAND`, `THIRDPERSON_RIGHTHAND`
- `Scale` - Changes the scaling sizes of the displayed item. Defaults to `.5,.5,.5` which matches item frame rendering. 

```yaml
  Furniture:
    Type: DISPLAY
    Height: 2
    Width: 2
    Scale: 2,2,2
```
#### Item_Frame
- `GlowingFrame` - Whether the frame should be a glowing frame which renders the furniture at 100% brightness at all times. Defaults to false.

## Drops
Furniture drops are defined under the furniture `Drops` section. This uses the standard MythicMobs drop table format.

By default the furniture will drop itself when broken if there is no Drops field defined. You can make the furniture drop nothing by setting `Drops: []` or `DropSelf: false`.
<br>If `DropSelf` is set to `true` and some `Drops` have been specified, then both the Furniture and the Drops will be dropped.

```yaml
  Furniture:
    Drops:
    - oak_planks 4
    - oak_log 2
```

## Furniture States

Furniture States are other states that furniture can be swapped into using the [`SetFurnitureState`](/Skills/Mechanics/setfurniturestate) mechanic.

This allows you to create dynamic furniture, such as:
- Crops that grow 
- A lamp that turns on or off
- Drawers that open and close

States are placed under a `States` section like so:
```yaml
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

## Examples
```yaml
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
```yaml
TestFurnitureStates:
  Id: BRICK
  Model: 2
  Display: 'Test States'
  Type: FURNITURE
  Furniture:
    Material: BRICK
    Model: 2
    Barriers:
    - 0,0,0
    DefaultState: BROKEN
    States:
      HALF_REPAIRED:
        Model: 3
        GlowingFrame: true
      REPAIRED:
        Model: 4
        Lights: true
        GlowingFrame: true
        GlowingItem: true
  FurnitureSkills:
  - setFurnitureState{state=BROKEN} ~onInteract
?furnitureState{s=REPAIRED}
  - setFurnitureState{state=REPAIRED} ~onInteract
?furnitureState{s=HALF_REPAIRED}
  - setFurnitureState{state=HALF_REPAIRED} ~onInteract
?furnitureState{s=BROKEN}```
```