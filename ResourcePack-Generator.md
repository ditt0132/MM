Crucible can be used to automatically generate some assets from item configurations to be drop-in ready for deployment to a resource pack!

[[_TOC_]]

# Usage

## Generation
This can be done via the use of the `/mythicmobs items generate` command

The Generation logic will:
  - Auto-detect if the path points to a `.json` or `.bbmodel` file.
  - If it's a bbmodel it will automatically extract the textures, mcmeta, and other relevant data
  - If nether are found, it will check for a `.png` in the textures folder and generate the item as a regular 2d sprite
  - Generate any necessary atlases

And all of the generated files will be put into the `Generation/` folder inside the `MythicMobs` main directory (`../plugins/MythicMobs/Generation/`).

The resulting resourcepack will be put in `../plugins/MythicMobs/Generation/resource_pack.zip`.

## Merging
A resource pack in `MythicMobs/Generation/merge` will automatically be merged into the generated pack, including any item overrides and atlases

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
If there are multiple numbered sounds, it will add those all as random options to the same sound e.g. growl1.ogg, growl2.ogg.  

If the top-level folder in Assets/sounds is a sound category, it will use that as the category.

All assets are generated in the `mythic:` namespace to avoid conflicts, including with custom blocks now (the sound mechanic will automatically detect these sounds so adding it manually isn't necessary)


## Fonts
Configured via the `font-images.yml` file.
Allows you to define custom image that is assigned to a special font characters that can be used in placeholders. Only the bitmap type is supported at this time. Can be found and used inside packs.

The file can contain multiple "entries". Each entry looks something like this:
```yaml
Donut:
     Type: bitmap
     Char: "\u6000"
     File: unicode/coverscreen/donut
     Ascent: 7
     Height: 15
```
These can be accessed using the placeholder <fontimage.donut> and can be used with the Text projectiles.  

The `Ascent` and `Height` options can be left empty: those values can be automatically calculated by Crucible if not specified.  

The `File` option can use images in the `minecraft:` namespace

```yaml
lightning:
  File: unicode/lightning

iron_boots:
  File: minecraft:item/iron_boots
```


# Item Configurations

## Basic Item Configuration
Generation settings are configured on the item in the `Generation` field/section.

The most basic way of doing this only requires you to set the Generation field like so:
```yaml
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
```yaml
EmeraldSword:
  Material: DIAMOND_SWORD
  Model: 1
  Generation:
    Model: item/emerald_sword   # The same as using Generation: [model]
    Parent: some/parent
    Textures:
    - override/texture
```


## Specific Item Types Options
Specific item types can have further special options to assign to every specific state they can have a different texture/model.

The value is the same as normal - can be a bbmodel or json in the models folder, or a png in the textures folder to generate a sprite.

- `Pulling` - for bows and crossbows
  - You can specify the pull after the texture: `item/bow/dirtbow_pulling_1 0.5`
  - If pull values aren't specified, vanilla defaults will be used if 3 entries are supplied. For more or less, it will interpolate more steps to try and to make them fit smoothly
- `Charged` - for crossbows
- `Firework` - for crossbows
- `Casting` - for fishing rods
- `Blocking` - for shields

```yaml
DonutBow:
  Material: BOW
  Generation:
    Model: item/bows/donut_bow
    Pulling:
    - item/bows/donut_bow_pulling_0
    - item/bows/donut_bow_pulling_1
    - item/bows/donut_bow_pulling_2
```

```yaml
TortoiseShield:
  Material: SHIELD
  Generation:
    Model: item/shields/tortoise_shield
    Blocking: item/shields/tortoise_shield_blocking
```


## Transformation Options
Allows you to quickly make color variants of items if you're into that sort of thing. Only really works with sprite items, flips and rotations etc don't work with models.
```yaml
TestGenerationSpriteColorize:
  Material: IRON_SWORD
  Model: 106
  Display: 'Blue Phoenix Sword'
  Generation:
    Texture: item/weapons/phoenix_sword
    Transform:
      FlipHorizontal: false
      FlipVertical: false
      Color: '#0000FF'
      HueShift: 0
      Saturation: 1.5
      Brightness: 1
```

# Examples

## Furniture

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
> The Generation fields also work on furniture and furniture states

## Items

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

## Blocks

```yml
  CustomBlock:
    Type: MUSHROOM_BLOCK
    Id: 18
    Texture: block/stars1
    # The texture here will default to a generic block with the texture on all sides.
```

## Armor Trims 

```yml
CopperHelmet:
  Material: CHAINMAIL_HELMET
  Model: 10
  # ^^^ The CustomModelData ID for the Material to use.
  # In this case, the model generated will be 
  # CHAINMAIL_HELMET with a CustomModelData ID of 10.
  Display: "<green>Copper Helmet"
  Generation:
    # vvv Texture is the inventory icon of your armor.
    Texture: item/armor/copper_helmet
    # vvv Armor references to the actual armor on the entity.
    # vvv Regarding the armor texture, it is based on 2 files, which
    # vvv should be named as the follows (based on copper armor):
    # vvv copper_layer_1.png # TOP PART
    # vvv copper_layer_2.png # BOTTOM PART - (keep in mind, you must use layer_1 and layer_2)
    Armor:
      Texture: armor/copper
      Type: TRIMS
      # ^^^ specify either TRIMS or SHADERS when both are enabled
```
```yml
  CustomArmor:
    Trims:
      Enabled: true
      GenerateDataPack: true
      HideBaseArmor:
      - CHAINMAIL
    Optifine:
      Enabled: false
    CoreShaders:
      Enabled: true
```
> config-generation.yml used for this example


# Configuration Files

## config-generation.yml
```yaml
Generation:
  # The namespace to use
  Namespace: mythic

  # If the ModelEngine resourcepack should be automatically merged
  MergeModelEngine: true

  # If the HappyHUD resourcepack should be automatically merged
  MergeHappyHUD: true

  # If the pack should be zipped
  ZipPack: true


  Deployment:
    
    # If the auto deployment feature is enabled
    Enabled: false

    # The type of the auto deployment. Can be SELFHOST or S3
    Type: SELFHOST

    # SELFHOST deployment options
    SelfHosting:

      # The port to use
      Port: 8080

    # S3 deployment options
    S3:
      Storage:
        Key: pack
        Bucket: packs
      Authentication:
        Endpoint: ''
        AccessKey: ''
        SecretKey: ''

    # If the resourcepack should be automatically sent to players
    AutoSend:
      Enabled: false
      SendOnUpdate: false
      PublicURL: https://s3.yourcoolwebsite.com


  CustomArmor:
    
    # What is the default generation method for custom armors. Can be NONE, TRIMS or SHADERS
    DefaultMethod: TRIMS

    # If the related optifine files should be generated
    GenerateOptifineFiles: true

    # Options for TRIMS
    Trims:
      Enabled: false
      GenerateDataPack: true

      # A list of armor types to hide in order to correctly override them
      HideBaseArmor: []

      # Causes any hidden armor types to be auto-converted to a trim that looks like the vanilla armor
      ConvertBaseArmor: true

    # Options for SHADERS
    Shaders:
      Enabled: false
      Shader: lessfancypants
```