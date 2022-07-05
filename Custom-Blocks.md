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