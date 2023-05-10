## Description
Sets the target player's held crossbow's CustomModelData and visualy sets it as either charged or not charged.

If an unloaded crossbow is set as "charged", the user will not be able to shoot the arrow.  
If a loaded crossbow is set as "not charged", the user will not be able to shoot the arrows in it until he loads another arrow or mechanic is used again to set it as "charged".  

Every time a loaded crossbow is set as "not charged", the arrow is stored. If the user loads multiple arrows and the mechanic is used each time before the user can shoot it, the arrows will add up. When the crossbow shoots, every arrow stored in it (up to *3*) will be launched in a "multishot" shaped pattern.

## Attributes
| Attribute      | Aliases     | Description                                             | Default |
|----------------|-------------|---------------------------------------------------------|---------|
| model          | m           | The new CustomModelData                                 | 0       |
| charged        |             | Should the crossbow be set as "charged"                 | true    |

## Examples
```yaml
TrickyCrossbow:
  Id: CROSSBOW
  Display: "Trick-y Crossbow"
  Skills:
  - setcrossbowcharged{m=3;charged=false} @self ~onSwing ?!crouching
  - setcrossbowcharged{m=4;charged=true}  @self ~onSwing ?crouching
```