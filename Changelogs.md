1.7.0 (dev builds)
=====

1.6.0
=====

Highlights
----------
- Custom blocks now usable in all MM mechanics and conditions
- Display entity furniture

Furniture
---------
### Display Entities (1.19.4+)
- Added support for DisplayEntity furniture with Furniture.Type option 
- All display options are also usable in furniture states
```
  Furniture:
    Type: DISPLAY
    Scale: 0.5,0.5,0.5 (size of the model, defaults to 0.5 to match itemframe sizing)
    Transform: [FIXED/HEAD/GROUND/GUI/LEFT_HAND/RIGHT_HAND, defaults to FIXED]
    Billboard: [FIXED/CENTER/VERTICAL/HORIZONTAL]
    Brightness: [brightness]
    InterpolationDelay: [delay before beginning interpolation]
    InterpolationDuration: [seconds to interpolate scaling over]
```
Type will default to DISPLAY on 1.19.4+ and ITEM_FRAME on earlier versions. DISPLAY should be backwards compatible with the default options. 

Old furniture should continue to work as normally and will auto-convert types if moved. 

If you're using ViaBackwards and can't use Display entities, set `Configuration.Furniture.DefaultType: ITEM_FRAME` in your config.yml

### Hitboxes (1.19.4+)
- Added hitbox support for furniture on 1.19.4+ using Interaction Entities.
```
Chair:
  Furniture:
    Hitbox:
      Height: 1
      Width: 1
```
Defaults to 1x1 if the furniture has no barriers, or 0 if it does.

### Timer Skills
- Furniture can now use timer skills

Mechanics
---------
### NEW: RemoveFurniture
- Removes the furniture that called the mechanic

### NEW: RemoveFurnitureAt
- Removes a furniture at the target location

Triggers
--------
- Added ~onPressF:HAND and ~onPressF:OFFHAND

Bug Fixes/Other
---------------
- Fixed several bugs with item updating
- Fixed ArrayIndexOutOfBoundsException in ItemManager
- Fixed bugs with glowing furniture
- Fixed `Options.Placeable`
- Fixed NPE in custom block loading with latest MM
- Fixed obscure dupe involving giving items from console
- Fixed several other potential dupe glitches
- Fixed rotating furniture not preserving the furniture's state
- Fixed `Furniture.CanRotate: false` not working
- Fixed onSwing not triggering when you hit something
- 

1.5.0
=====

Highlights
----------
- [Custom Blocks](Custom-Blocks)
- [Crafting](Recipes)
- [Bags](Bags)
- [Furniture States](Furniture-States)

General
-------

Items
-----
- Added `Options.Placeable` for regular items, defaults to false
- Added `Options.PreventEnchanting`
- Added `Options.PreventAnvil`

Custom Blocks
-------------
- Added [custom blocks](Custom-Blocks)
- Can use block states of mushroom blocks or noteblocks to create custom blocks
  - Using noteblocks will disable noteblocks in survival on your server
- Added pickblock support for custom blocks
- Added worldedit support for custom blocks using `//set mythic:name`
- Added `/crucible generate` command to generate blockstate files for any custom blocks that are loaded
- See page for more info

Furniture
---------
- Added `Furniture.DropSelf` defaults to true in most cases
- Added pickblock support for furniture
- Added some real API methods for placing furniture
- Added `GlowingFrame: true` option to use a glowing item frame, which will make the furniture always have maximum brightness
- Added `GlowingItem: true` option to make the furniture itself glow with an outline
- Added Furniture States

Bags
---------------
- Added [Bags], allowing you to turn items into bags
- See [Bags] page for more info

Custom Crafting
---------------
- Can register crafting recipes for items
- See [Recipes] page for more info

### States

Bug Fixes/Other
---------------
- Fixed furniture not being placeable where there was previously furniture that didn't use barrier blocks
- Fixed onAttack triggering even if event is cancelled
- Fixed ArrayIndexOutOfBoundsException in ItemManager
- Fixed item skills still being usable after breaking from custom durability
- Fixed non-lowercase items not working in shaped crafting
- Fixed some errors with furniture hitboxes
- Fixed a bunch of other assorted furniture bugs

1.4.0
=====

Highlights
----------
- Added Furniture

Older Changelogs
================
-   [1.5.X Changelogs](/1.5.x_changelogs)
-   [1.4.X Changelogs](/1.4.x_changelogs)
-   [1.3.X Changelogs](/1.3.x_changelogs)
-   [1.2.X Changelogs](/1.2.x_changelogs)
-   [1.1.X Changelogs](/1.1.x_changelogs)
-   [1.0.X Changelogs](/1.0.x_changelogs)
-   [Pre-1.0.0 Changelogs](/pre-1.0_changelogs)}