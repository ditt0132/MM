An item type whose utility is related to furnitures.

- Hitting furniture that has `Colorable: true` enabled will apply the brush's color to the furniture.
- Material must be colorable (leather for best results).
- Using leather armor as the brush base allows players to apply different dyes the same way they do with regular leather armor
- the `onPaint` trigger works specifically for paint brush items

```yaml
TestPaintBrush:
  Material: LEATHER_BOOTS
  Display: 'Paint Brush'
  Type: PAINT_BRUSH
  Options:
    Color: 0,0,255
  Skills:
  - particles{p=reddust;size=<random.1to5>;color=<item.color.hex>;a=5;hS=0.5;vS=0.5} @origin ~onPaint
```