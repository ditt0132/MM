## Description
Sets the casting Furniture's [State](/Furniture#furniture-states) as the specified one

## Attributes
| Attribute      | Aliases     | Description                                             | Default Value |
|----------------|-------------|---------------------------------------------------------|---------------|
| state          |             | The name of the new state the Furniture should have     |               |

## Examples
```yaml
  FurnitureSkills:
  - furniturestate{state=OPEN} @self ~onInteract ?furnitureState{s=CLOSED}
  - furniturestate{state=CLOSED} @self ~onInteract ?furnitureState{s=OPEN}
```

## Aliases
- [x] setfurniturestate