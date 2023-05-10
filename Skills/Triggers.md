Crucible supports all triggers that generally make sense, and also adds a bunch of new skill triggers for use by items. This list contains all compatible triggers.

| Trigger        | When it fires…                                                                                                                                                                                                                        |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| onAttack       | When the player hits another entity                                                                                                                                                                                                   |
| onBlockBreak   | When the player breaks a block                                                                                                                                                                                                        |
| onBlockPlace   | When the player places a block                                                                                                                                                                                                        |
| onConsume      | Triggered if the item is food or a potion that is eaten                                                                                                                                                                               |
| onCrouch       | When the player crouches                                                                                                                                                                                                              |
| onUnCrouch     | When the player stops crouching                                                                                                                                                                                                       |
| onDamaged      | When the player is damaged                                                                                                                                                                                                            |
| onDeath        | When the player dies                                                                                                                                                                                                                  |
| onEquip        | When a player equips an armor piece.                                                                                                                                                                                                  |
| onUnEquip      | When a player unequips an armor piece.                                                                                                                                                                                                |
| onInteract     | When the player interacts with an entity                                                                                                                                                                                              |
| onBowHit       | When a player hits an entity with an arrow                                                                                                                                                                                            |
| onPotionSplash | Triggered if the item is a potion that was thrown                                                                                                                                                                                     |
| onRightClick   | When the player right-clicks                                                                                                                                                                                                          |
| onShoot        | When the player shoots a bow                                                                                                                                                                                                          |
| onSpawn        | When the player logs in or respawns                                                                                                                                                                                                   |
| onSwing        | When the player left-clicks                                                                                                                                                                                                           |
| onTimer:#      | Every # ticks (where # is the interval in ticks)                                                                                                                                                                                      |
| onUse          | When the player right-clicks while holding the item                                                                                                                                                                                   |
| onFish         | When the player right-clicks while holding a fishing rod                                                                                                                                                                              |
| onFishBite     | When a fish bites the hook from a fishing rod                                                                                                                                                                                         |
| onFishCatch    | When the fish latches onto the hook from a fishing rod                                                                                                                                                                                |
| onFishGrab     | When the player right-clicks while holding the fishing rod with a latched fish                                                                                                                                                        |
| onFishGround   | When the bobber is stuck in the ground                                                                                                                                                                                                |
| onFishingReel  | When the player reels in a fishing rod with no fish on the other end                                                                                                                                                                  |
| onFishingFail  | When the player fails a fish attempt due usually due to poor timing                                                                                                                                                                   |
| onPressQ       | When a player presses Q to drop the item. Requires ProtocolLib                                                                                                                                                                        |
| onPressCtrlQ   | When a player presses CTRL+Q to drop the item. Requires ProtocolLib                                                                                                                                                                   |
| onPressF       | When a player presses F to swap the item. Requires ProtocolLib                                                                                                                                                                        |
| onPressF_HAND | When a player presses F to swap the item, and it ends up in the main hand. Requires ProtocolLib                                                                                                                                                                        |
| onPressF_OFFHAND | When a player presses F to swap the item, and it ends up in the offhand. Requires ProtocolLib                                                                                                                                                                        |
| onPress        | When a player presses a key. Requires [MythicKeysPlugin](https://www.spigotmc.org/resources/mythickeysplugin-custom-keybinds-api.98893/) for the server and [MythicKeys mod](https://github.com/ASangarin/MythicKeys) for the client  |
| onRelease      | When a player releases a key. Requires [MythicKeysPlugin](https://www.spigotmc.org/resources/mythickeysplugin-custom-keybinds-api.98893/) for the server and [MythicKeys mod](https://github.com/ASangarin/MythicKeys) for the client |
| onJoin         | When a player joins the server                                                                                                                                                                                                        |
| onRespawn      | When a player respawns                                                                                                                                                                                                                |
| onPickup       | When a player picks up a crucible item                                                                                                                                                                                                |
| onHold         | When the player holds an item                                                                                                                                                                                                         |
| onUnHeld      | When the player switches off the item from their hotbar                                                                                                                                                                               |
| onFurnitureStateChange | When the [Furniture](/wikis/Furniture) changes state.                                                                                                                                                                               |


Example Usages
--------

**MythicKeys Triggers**
```yml
COOL_ITEM:
  Id: STICK
  Display: I'm a cool stick
  Skills:
    - message{m="You pressed the jump key"} @Self ~onPress ?keyid{id=minecraft:jump}
    - message{m="You released the jump key"} @Self ~onRelease ?keyid{id=minecraft:jump}
```