1.5.0
=====

Highlights
----------
- [Custom Blocks](Custom-Blocks)
- [Crafting](Recipes)
- [Bags](Bags)
- Furniture States[](https://git.mythiccraft.io/mythiccraft/mythiccrucible/-/wikis/Furniture-States)

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