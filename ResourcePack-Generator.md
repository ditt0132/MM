# Introduction

Crucible can be used to automatically generate some assets from item configurations to be drop-in ready for deployment to a resource pack!


The Generation logic will:
  - Auto-detect if the path points to a `.json` or `.bbmodel` file.
  - If it's a bbmodel it will automatically extract the textures, mcmeta, and other relevant data
  - If nether are found, it will check for a `.png` in the textures folder and generate the item as a regular 2d sprite
  - Will generate any necessary atlases
  - The Generation fields also work on furniture and furniture states
  - Export a resource pack ready to merge with your own in `Plugins/MythicMobs/Generation/resource_pack.zip`.

And all of the generated files will be put into the `Generation/` folder inside the `MythicMobs` main directory (`../plugins/MythicMobs/Generation/`).

# Usage
This can be done via the use of the `/mythicmobs items generate` command


# Packs
Packs can now contain an "Assets" folder with the following layout:
```
Pack
  |-- Assets
      |-- models (.json or .bbmodel files, can use subfolders to organize)
      |-- textures (textures, can use subfolders to organize)
      |-- sounds (.ogg sound files, can use subfolders to organize)
```
The contents of these folders should be similar to an actual resource pack. In the example item [HERE](#items), it would copy the texture file `Assets/textures/item/clubs/putter.png`.  

Items will be generated **using the configured Material and Model numbers**, and will output a warning if duplicates are detected.  

## Sounds
The structure of the sounds folder will be used to generate a sounds.json.
`Assets/sounds/entity/cerberus/growl.ogg` would generate a sound at `entity.cerberus.growl`.  
If there are multiple numbered sounds, it will add those all as random options to the same sound e.g. growl1.ogg, growl2.ogg

All assets are generated in the `mythic:` namespace to avoid conflicts, including with custom blocks now (the sound mechanic will automatically detect these sounds so adding it manually isn't necessary)

## Basic Item Configuration
Generation settings are configured on the item in the `Generation` field/section.

The most basic way of doing this only requires you to set the Generation field like so:
```
EmeraldSword:
  Material: DIAMOND_SWORD
  Model: 1
  Generation: item/emerald_sword
```
This will do the following:
- Check `Pack/Assets/models` for `item/emerald_sword.bbmodel` or `item/emerald_sword.json`
- If neither of those exist, it will check `Pack/Assets/textures` for `item/emerald_sword.png`

...so by setting only the Generation field, the generator will auto-detect between the 3 different options for custom items: a .bbmodel model, a .json model, or a regular sprite image.

If the model is a `.bbmodel` file, your work is done! The generator will extract the textures and mcmeta files for you automatically. However, if you are using a `.json` model, the generator will read the textures from the .json file and look for them in the `Pack/Assets/textures` folder (similar to how a resource pack works) and use those.

The Material and CustomModelId of the Mythic item will be used for generating the pack.

## Advanced Item Configuration
Generation supports other options as well for more advanced usage. 
```
EmeraldSword:
  Material: DIAMOND_SWORD
  Model: 1
  Generation:
    Model: item/emerald_sword   # The same as using Generation: [model]
    Parent: some/parent
    Textures:
    - override/texture
```

## Examples

### Furniture

```yml
TestGeneration5:
  Material: LEATHER_BOOTS
  Model: 10 
  # ^^^ The CustomModelData ID for the Material to use.
  # In this case, the model generated will be 
  # LEATHER_BOOTS with a CustomModelData ID of 10.
  Display: 'Test Generation 5'
  Generation: item/toilet 
  # ^^^ This denotes the file structure for the item's model to be placed.
  Type: FURNITURE
  Furniture:
    Type: DISPLAY
    Material: BRICK
    Model: 11
    # Furniture states are also accounted for in the same way.
    # For example, item/toilet would be BRICK CMD 11
    Generation: item/toilet
    States:
      UH_OH:
        Model: 12
        Generation: item/toilet_flushed
        # And this would be BRICK CMD 12
```

### Items

```yml
GolfPutter:
  Material: IRON_HOE
  Model: 1
  Display: 'TGolf Club (Putter)'
  Generation:
    Model: item/clubs/putter
    # The json or bbmodel file named "putter" in the pack
    # if no Model is defined, it will default to an extruded texture (think diamonds)
    Textures:
    - item/clubs/putter
    # Textures is optional, best for if there is more than 1 texture on a model.
```

### Blocks

```yml
  CustomBlock:
    Type: MUSHROOM_BLOCK
    Id: 18
    Texture: block/stars1
    # The texture here will default to a generic block with the texture on all sides.
```