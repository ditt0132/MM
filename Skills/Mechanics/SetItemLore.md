Mechanic: SetItemLore
================

Sets the new lore of the item

Attributes
----------

| Attribute | Aliases |       Description        | Default |
|:---------:|:-------:|:------------------------:|:-------:|
|   lore    |    l    | The new lore of the item |         |



Examples
--------
This changes the item's lore whenever a player right clicks with the item.
```yaml
MyItem:
  Id: stick
  Display: 'Godly Stick'
  Lore:
    - 'This is line 1'
    - 'This is line 2'
  Skills:
    - setitemlore{l="This is line 1","Is this line 2"} ~onUse
```