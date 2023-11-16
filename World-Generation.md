The WorldGen feature allows you to configure how certain blocks (both vanilla ones and crucible ones) will be generated in the world.  

This feature can be configured via the `worldgen.yml` file.

## worldgen.yml
Blocks to be generated can be added as "entries" under the `CustomBlocks` key like so
```yaml
CustomBlocks:
     SpecialBlock:
       Block: TestBlock
       Worlds:
       - world
       Environment: NORMAL
       Chance: 0.2
       Depth:
         Min: -50
         Max: 20
       Vein:
         Count: 1
         Size: 5
       Replace:
       - STONE
       - DEEPSLATE
       Bordering:
       - AIR
       NotBordering:
       - AIR
       Conditions: []
```