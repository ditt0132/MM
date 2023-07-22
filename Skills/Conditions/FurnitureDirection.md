## Description
Checks if the targeted Furniture entity has a specific direction


## Attributes
| Attribute      | Aliases     | Description                                                  | Default  |
|----------------|-------------|--------------------------------------------------------------|----------|
| direction      | dir, d      | The direction to check for                                   |          |

### Direction Attribute
The possibile direction values can be `NORTH`, `NORTH_WEST`, `WEST`, `SOUTH_WEST`, `SOUTH`, `SOUTH_EAST`, `EAST`, `NORTH_EAST`,


## Example
```yaml
  Conditions:
  - furnitureDirection{d=NORTH} true
```