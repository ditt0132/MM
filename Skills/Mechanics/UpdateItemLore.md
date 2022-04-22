Mechanic: UpdateItemLore
================

Parses placeholders in the item's lore config.

Attributes
----------
This mechanic does not have any attributes.

Examples
--------

```yaml
MyItem:
  Id: stick
  Display: 'Godly Stick'
  Lore:
    - 'This is a random number <random.0to5>'
  Skills:
    - updateitemlore{} ~onUse
```