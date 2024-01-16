## Description
This condition checks if the furniture you are targeting is a specific type of furniture.

## Attributes
| Attribute | Aliases   | Description                                                          | Default |
|-----------|-----------|----------------------------------------------------------------------|---------|
| type | t   | The type to check for |  |

## Examples
```yaml
  TargetConditions:
  - furnitureType{type=BrownCouch} true
```