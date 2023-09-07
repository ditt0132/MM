# Placeholders
------------

These are all of the placeholders MythicCrucible provides.


Caster Placeholders
------------------
These placeholders will return whatever attribute of the caster that is called.

```yaml
Skills:
  - message{m="<caster.item.nbt.TestKey|Unknown>"} @self ~onSwing
  - message{m="<caster.item.hand.nbt.Some.Other_Key|5>"} @self ~onSwing
```
Put a value to use after "|" inside the placeholder to provide a default when the value is undefined.

|         Caster Placeholder         | Function                                                          |
|:----------------------------------:|-------------------------------------------------------------------|
|       <caster.item.nbt.KEY>              | If no slot is specified, this checks the caster's item that called the skill.                   |
|      <caster.item.hand.nbt.KEY>              | Returns the specified NBT key of the caster's hand item.                               |
|      <caster.item.offhand.nbt.KEY>              | Returns the specified NBT key of the caster's offhand item.                        |
|      <caster.item.head.nbt.KEY>              | Returns the specified NBT key of the caster's head item.                               |
|      <caster.item.chest.nbt.KEY>              | Returns the specified NBT key of the caster's head item.                           |
|      <caster.item.legs.nbt.KEY>              | Returns the specified NBT key of the caster's head item.                               |
|      <caster.item.feet.nbt.KEY>              | Returns the specified NBT key of the caster's feet item.                               |

**Trigger Placeholders**
-----------------
These placeholders will return whatever attribute of the item that caused the skill to happen.

-----------------
| Trigger Placeholders | Function                                                                               |
|:--------------------:|----------------------------------------------------------------------------------------|
|    <trigger.item.hand.nbt.KEY>    | Returns the specified NBT key of the trigger's hand item.                                    |

-----------------
| Stat Placeholders | Function                                                                               |
|:--------------------:|----------------------------------------------------------------------------------------|
|    <stat.STAT_NAME>    | Returns the value of the specified stat.                                    |