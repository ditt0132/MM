## Description
This condition checks the direction the targeted furniture is facing.

*Note: This condition seems unable to determine diagonal directions*

## Attributes
| Attribute | Aliases   | Description                                                          | Default |
|-----------|-----------|----------------------------------------------------------------------|---------|
| direction | d   | The direction to check for |  |

## Examples
```yaml
  TargetConditions:
  - furnitureDirection{d=EAST} true
```