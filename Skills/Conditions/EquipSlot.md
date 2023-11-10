## Description
This condition checks if the player has the Crucible item equipped in a particular slot. This condition does not work for other materials, only the item running the skill. for a skill to check for materials for more complex checks, see the [wearing](https://git.mythiccraft.io/mythiccraft/MythicMobs/-/wikis/skills/conditions/wearing) condition.


## Attributes
| Attribute | Aliases   | Description                                                          | Default |
|-----------|-----------|----------------------------------------------------------------------|---------|
| EquipSlot | slot, s   | The item slot to check                                               | HAND    |

### EquipSlot attribute
Valid Slots:
- `HEAD`
- `CHEST`
- `LEGS`
- `FEET`
- `HAND`
- `OFFHAND`


## Examples
```yaml
  Conditions:
  - equipslot{slot=HAND} true
```


## Aliases
- [x] equipmentslot
- [x] wornslot