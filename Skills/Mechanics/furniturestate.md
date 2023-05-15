## Description
Sets the casting Furniture's [State](/Furniture#furniture-states) as the specified one

## Attributes
| Attribute      | Aliases     | Description                                             | Default Value |
|----------------|-------------|---------------------------------------------------------|---------------|
| state          |             | The name of the new state the Furniture should have     |               |

## Examples
```yaml
#ITEM CONFIG
ExampleFurniture:
  Id: STONE
  Display: "Example Furniture"
  Type: FURNITURE
  Furniture:
    Material: BRICK
    DefaultState: CLOSED
    States:
      OPEN:
        Model: 6
      CLOSED:
        Model: 7
  FurnitureSkills:
  - skill{s=ExampleFurniture_SwitchState} @self ~onInteract
```
```yaml
#SKILL CONFIG
ExampleFurniture_SwitchState:
  Conditions:
  - furnitureState{s=CLOSED} orElseCast ExampleFurniture_Close
  Skills:
  - furniturestate{state=OPEN}

ExampleFurniture_Close:
  Skills:
  - furniturestate{state=CLOSED}
```

## Aliases
- [x] setfurniturestate