## Description
Switches the item's CustomModelData value between two specified ones each time this mechanic is triggered

## Attributes
| Attribute      | Aliases     | Description                                             | Default Value |
|----------------|-------------|---------------------------------------------------------|---------------|
| model1         |             | The first CustomModelData value                         |               |
| model2         |             | The second CustomModelData value                        |               |


## Examples
```yaml
  Skills:
  - modeltoggle{model1=10;model2=30} @self ~onUse
```

## Alias
  - [x] togglemodel