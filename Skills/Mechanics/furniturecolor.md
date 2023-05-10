## Description
Sets the casting Furniture's [Color](/Furniture#color) as the specified one

## Attributes
| Attribute      | Aliases     | Description                                             | Default Value |
|----------------|-------------|---------------------------------------------------------|---------------|
| color          | c           | The name of the new state the Furniture should have     | #FFFFFF       |

## Examples
```yaml
  FurnitureSkills:
  - furniturecolor{color=#cc0000} @self ~onInteract
```

## Aliases
- [x] setfurniturecolor