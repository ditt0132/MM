## Description
Removes the furniture at the target location

## Attributes
| Attribute      | Aliases     | Description                                             | Default Value |
|----------------|-------------|---------------------------------------------------------|---------------|
| doDrops        |             | If the Furniture should drops its Drops once removed    | false         |

## Examples
```yaml
  FurnitureSkills:
  - removefurnitureat{doDrops=true} @selflocation{xoffset=1} ~onInteract
```