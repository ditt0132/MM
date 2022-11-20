Custom Blocks
---------
Crucible allows people to create "custom blocks" using the extra block states from mushroom blocks, note blocks, or tripwires.

Items that are configured to be blocks will have their corresponding block placed in the world where the player is looking when right-clicked, and will drop the original item when broken by default (unless configured otherwise).

Custom Block Options
-----------------
All options are placed under a "CustomBlock" section on an item.

### Base Options
- `Type` - The type of custom block, defaults to mushroom (MUSHROOM_BLOCK, NOTE_BLOCK, or TRIPWIRE)
- `Id` - The ID of the custom block.

Putting in Resource Pack
------------------------
Crucible can automatically generate the blockstate and model files for you to put in your resource pack. It will only generate files for the types of blocks that have custom blocks configured for them.

To do so, simply type `/crucible generate` in the console or in-game and the files will generate in `plugins/MythicCrucible/resourcepack`.

By default, the block models will generate pointing to:
- `block/custom/mushroom_#` for mushroom blocks
- `block/custom/noteblock_#` for noteblocks
... where # is the ID that has been configured.

So for example, default you'd want to put a texture file for Mushroom block 1 in your resource pack located in:
- `assets/minecraft/textures/block/custom`, named `mushroom_1.png`

Example Configuration
---------------------
```
TestBlock:
  Id: STONE
  Model: 5
  Display: 'Probably a Block'
  Type: BLOCK
  CustomBlock:
    Type: MUSHROOM_BLOCK
    Id: 30
  CustomBlockSkills:
  - sound{s=block.amethyst_block.place} @self ~onBlockPlace
  - sound{s=block.amethyst_block.break} @self ~onBlockBreak
```