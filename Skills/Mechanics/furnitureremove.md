## Description
Removes the furniture that casted the mechanic

## Attributes
| Attribute      | Aliases     | Description                                             | Default  |
|----------------|-------------|---------------------------------------------------------|----------|
| doDrops        |             | If the Furniture should drop its Drops once removed     | false    |

## Examples
```yaml
  FurnitureSkills:
  - removefurniture{doDrops=true} @self ~onInteract
```

## Aliases
- [x] removefurniture