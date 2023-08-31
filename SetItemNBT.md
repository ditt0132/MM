## Description
Sets an NBT value on an item

## Attributes
| Attribute      | Aliases     | Description                                             | Default |
|----------------|-------------|---------------------------------------------------------|---------|
| key          |            | The NBT key                                 | NONE       |

## Examples
```yaml
  Skills:
  - setItemNBT{key=some_key;value=<caster.name>} @self ~onUse

  - setItemNBT{slot=HEAD;key=some_key;value=int/5} @self

  - setItemNBT{key=some.other_key;value=double/5}
```