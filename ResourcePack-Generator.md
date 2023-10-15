# Introduction
The ResourcePack Generator feature allows you to generate a resourcepack from the items and blocks you have configured.


# Usage
## Generate the Resourcepack
This can be done via the use of the `/crucible generate` command

## Configure the Items
Generation settings are configured on the item. If no textures are specified, it will attempt to read the model and derive the textures from that
```yaml
GolfPutter:
  Material: IRON_HOE
  Model: 1
  Display: 'TGolf Club (Putter)'
  Generation:
    Model: item/clubs/putter
    Textures: # this is optional
    - item/clubs/putter
```

# Packs
Packs can now contain an "Assets" folder with the following layout
```
Pack
|-- Assets
  |-- blueprints (for bbmodels, not implemented yet)
  |-- models (json model files)
  |-- textures
  |-- sounds
```
The contents of these folders should be similar to an actual resource pack. In the example item, it would copy the texture file `Assets/textures/item/clubs/putter.png`.  

Items will be generated **using the configured Material and Model numbers**, and will output a warning if duplicates are detected.  

## Sounds
The structure of the sounds folder will be used to generate a sounds.json.
`Assets/sounds/entity/cerberus/growl.ogg` would generate a sound at `entity.cerberus.growl`.  
If there are multiple numbered sounds, it will add those all as random options to the same sound e.g. growl1.ogg, growl2.ogg

All assets are generated in the `mythic:` namespace to avoid conflicts, including with custom blocks now (the sound mechanic will automatically detect these sounds so adding it manually isn't necessary)