## Description
Opens an inventory with a specified amount of slots and name to the target player. The inventory is persistent and is dropped once the Furniture breaks.  


Opening inventories with different amounts of slots is **not possible**: the first time an inventory is opened, the specified amount of slots is registered as the "correct" one, and trying to use the mechanic with a different amount will not work.  


It is however **possible** to change the *name* of the inventory every time it is opened, and as long as the number of slots is constant the mechanic will open the same inventory, but with the specified name as the inventory's name.  


The number of slots of the inventory can be `9`,`18`,`27`,`36`,`45`,`54`.

## Attributes
| Attribute      | Aliases     | Description                                             | Default       |
|----------------|-------------|---------------------------------------------------------|---------------|
| title          | t           | The name displayed in the inventory        |The Display name of the Item|
| size           | s           | The number of slots of the inventory                    | 9             |


## Examples
```yaml
  FurnitureSkills:
  - FurnitureInventory{title="A Chest! more or less...";size=27} @trigger ~onInteract
```

##
In this example you can see how it is possible to change the inventory name, since an inventory is bound to the casting furniture, and not its name
```yaml
  FurnitureSkills:
  - randomskill{s=
    [
      - FurnitureInventory{title="Hello";size=54}
    ],
    [
      - FurnitureInventory{title="World";size=54}
    ]
    } @trigger ~onInteract
```

## Aliases
  - [x] openfurnitureinventory