## Description
Sets the specified CustomModelData on the item on the specified slot

## Attributes
| Attribute      | Aliases     | Description                                             | Default |
|----------------|-------------|---------------------------------------------------------|---------|
| model          | m           | The new CustomModelData                                 | 0       |
| equipslot      | slot, s     | The slot of the item                                    | HEAD    |

## Examples
```yaml
  Skills:
  - modelsetslot{m=3;slot=HAND} @self ~onUse
```

## Aliases
  - [x] setslotmodel