## Description
Sets the specified CustomModelData on the item the caster is holding

## Attributes
| Attribute      | Aliases     | Description                                             | Default |
|----------------|-------------|---------------------------------------------------------|---------|
| model          | m           | The new CustomModelData                                 | 0       |

## Examples
```yaml
  Skills:
  - setitemmodel{m=3} @self ~onUse
```

## Aliases
  - [x] modelset
  - [x] setmodel
  - [x] setitemmodel