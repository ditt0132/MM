## Description
Sets a furniture at the target location


## Attributes
| Attribute      | Aliases     | Description                                                  | Default  |
|----------------|-------------|--------------------------------------------------------------|----------|
| furniture      | f           | The Furniture to place                                       |          |
| yaw            | y           | The yaw of the furniture                                     | 0        |
| overwrite      | ow, force   | If the mechanic should remove any furniture at the target location before placing its own                                                                               | false    |
| dodrops     | drops, drop, d |If the overwritten Furniture should drop its Drops once removed | false  |


## Examples
```yaml
  Skills:
  - furnitureSetAt{f=MyFurniture} @Forward{f=2}
```


## Aliases
- [x] setFurnitureAt