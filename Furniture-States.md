An example of how furniture states is used.

```TestFurnitureStates:
  Id: BRICK
  Model: 2
  Display: 'Test States'
  Type: FURNITURE
  Furniture:
    Material: BRICK
    Model: 2
    Barriers:
    - 0,0,0
    DefaultState: BROKEN
    States:
      HALF_REPAIRED:
        Model: 3
        GlowingFrame: true
      REPAIRED:
        Model: 4
        Lights: true
        GlowingFrame: true
        GlowingItem: true
  FurnitureSkills:
  - setFurnitureState{state=BROKEN} ~onInteract
?furnitureState{s=REPAIRED}
  - setFurnitureState{state=REPAIRED} ~onInteract
?furnitureState{s=HALF_REPAIRED}
  - setFurnitureState{state=HALF_REPAIRED} ~onInteract
?furnitureState{s=BROKEN}```