Mechanic: UpdateLore
================

Reparses the lore in your item config

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
    - updatelore{} ~onUse
```