Mechanic: SetItemDisplay
================

Sets the item display name

Attributes
----------

| Attribute | Aliases |            Description             | Default |
|:---------:|:-------:|:----------------------------------:|:-------:|
|  display  |    d    | The new displayed name of the item |         |



Examples
--------
This changes the item's display name from "Godly Stick" to "This is my new name!" whenever a player right clicks with the item.
```yaml
MyItem:
  Id: stick
  Display: 'Godly Stick'
  Skills:
    - setitemdisplay{d="This is my new name!"} ~onUse
```