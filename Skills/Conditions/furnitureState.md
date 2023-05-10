## Description
Checks if the target Furniture's [State](/Furniture#furniture-states) is the specified one

## Attributes
| Attribute      | Aliases     | Description                                             | Default Value |
|----------------|-------------|---------------------------------------------------------|---------------|
| state          |             | The state to check for                                  |               |

## Examples
```yaml
  Conditions:
  - furnitureState{s=BROKEN} true
```