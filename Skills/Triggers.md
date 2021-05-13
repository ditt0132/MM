Crucible supports all triggers that generally make sense, and also adds a bunch of new skill triggers for use by items. This list contains all compatible triggers.

| Trigger        | When it fires…                                                                 |
|----------------|--------------------------------------------------------------------------------|
| onAttack       | When the player hits another entity                                            |
| onBlockBreak   | When the player breaks a block                                                 |
| onBlockPlace   | When the player places a block                                                 |
| onConsume      | Triggered if the item is food or a potion that is eaten                        |
| onCrouch       | When the player crouches                                                       |
| onUnCrouch     | When the player stops crouching                                                |
| onDamaged      | When the player is damaged                                                     |
| onDeath        | When the player dies                                                           |
| onInteract     | When the player interacts with an entity                                       |
| onBowHit       | When a player hits an entity with an arrow                                     |
| onPotionSplash | Triggered if the item is a potion that was thrown                              |
| onRightClick   | When the player right-clicks                                                   |
| onShoot        | When the player shoots a bow                                                   |
| onSpawn        | When the player logs in or respawns                                            |
| onSwing        | When the player left-clicks                                                    |
| onTimer:#      | Every # ticks (where # is the interval in ticks)                               |
| onUse          | When the player right-clicks while holding the item                            |
| onFish         | When the player right-clicks while holding a fishing rod                       |
| onFishBite     | When a fish bites the hook from a fishing rod                                  |
| onFishCatch    | When the fish latches onto the hook from a fishing rod                         |
| onFishGrab     | When the player right-clicks while holding the fishing rod with a latched fish |
| onFishGround   | When the bobber is stuck in the ground                                         |
| onFishingReel  | When the player reels in a fishing rod with no fish on the other end           |
| onFishingFail  | When the player fails a fish attempt due usually due to poor timing            |
| onPressQ       | When a player presses Q to drop the item. Requires ProtocolLib                 |
| onPressCtrlQ   | When a player presses CTRL+Q to drop the item. Requires ProtocolLib            |
| onPressF       | When a player presses F to swap the item. Requires ProtocolLib                 |
| onEquip        | When a player equips an armor piece.                                           |
| onUnEquip      | When a player unequips an armor piece.                                         |