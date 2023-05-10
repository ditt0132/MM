## Description 
Modifies the custom durability of the held item.

## Attributes
| Attribute | Aliases |       Description         | Default |
|-----------|---------|---------------------------|---------|
|   amount  | a       | Adds/Subtracts durability |   1     |

## Examples
A positive number will deal damage, a negative number will heal it.
**Note:** Only works for custom durability.

```yaml
MyItem:
  Id: golden_sword
  Display: 'Excalibur'
  CustomDurability:
    Durability: 20
  Lore:
    - 'This is line 1'
    - 'This is line 2'
  Skills:
    - dealcustomdurability{a=2} @Self ~onUse    # damages an item by 2 durability.
    - dealcustomdurability{a=-2} @Self ~onSwing # repairs 2 durability on an item.
```

## Aliases
  - [x] dealdura
  - [x] customdura