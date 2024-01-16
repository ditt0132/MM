## Description
Targets all MythicCrucible furniture in a radius around the caster


## Attributes
| Attribute | Aliases   | Description                                                          | Default |
|-----------|-----------|----------------------------------------------------------------------|---------|
| radius    | r         | The radius of the targeter                                           |        |
| types     | type, t   | The type of the target Furniture.                  |         |


## Examples
```yaml
ExampleSkill:
  Skills:
  - removefurniture{doDrops=true} @FurnitureInRadius{r=16;types=BrownCouch}
```