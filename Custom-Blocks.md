Crucible allows people to create "custom blocks" using the extra block states from mushroom blocks, note blocks, or tripwires.

Items that are configured to be blocks will have their corresponding block placed in the world where the player is looking when right-clicked, and will drop the original item when broken by default (unless configured otherwise).


## Custom Block Options
All options are placed under a `CustomBlock` section on an item.

### Base Options
- `Type` - The type of custom block, defaults to mushroom (MUSHROOM_BLOCK, NOTE_BLOCK, or TRIPWIRE)
- `Id` - The ID of the custom block.
- `Texture` - The path of the texture the block will use

```yaml
  CustomBlock:
    Type: MUSHROOM_BLOCK
    Id: 18
    Texture: block/stars1
```

## Putting in Resource Pack
Please refer to the [Resourcepack Generator](ResourcePack-Generator) wiki page for info.

## Example
```yaml
TestBlock:
  Id: STONE
  Model: 5
  Display: 'Probably a Block'
  Type: BLOCK
  CustomBlock:
    Type: MUSHROOM_BLOCK
    Id: 30
    Texture: block/exampletexture
  CustomBlockSkills:
  - sound{s=block.amethyst_block.place} @self ~onBlockPlace
  - sound{s=block.amethyst_block.break} @self ~onBlockBreak
```


## WorldEdit Support
You can place custom blocks using worldedit via the following syntax:
```
//set mythic:ItemName
```