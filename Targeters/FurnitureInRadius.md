## Description
Targets all the furniture in a radius, optionally filtering for some of them


## Attributes
| Attribute | Aliases   | Description                                                          | Default |
|-----------|-----------|----------------------------------------------------------------------|---------|
| radius    | r         | The radius of the targeter                                           | 5       |
| types     | type, t   | A list of furniture types to check against                           |         |


## Examples
```yaml
  Skills:
  - particle @FurnitureInRadius{r=10}
```
```yaml
  Skills:
  - particle @FurnitureInRadius{r=10;types=Example_Furniture}
```
```yaml
  Skills:
  - particle @FurnitureInRadius{r=10;types=Chair,Table}
```


## Aliases
- [x] FIR