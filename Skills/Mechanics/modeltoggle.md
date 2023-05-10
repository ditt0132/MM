## Description
Switches the item's CustomModelData value between two specified ones each time this mechanic is triggered

## Attributes
| Attribute      | Aliases     | Description                                             | Default       |
|----------------|-------------|---------------------------------------------------------|---------------|
| model1         |             | The first CustomModelData value                         |  0            |
| model2         |             | The second CustomModelData value                        |  0            |


## Examples
```yaml
  Skills:
  - modeltoggle{model1=10;model2=30} @self ~onUse
```

## Alias
  - [x] togglemodel