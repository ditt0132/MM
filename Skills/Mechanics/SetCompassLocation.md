## Description
Sets the location a compass points to. Compass will point to whatever targeter you use.

## Attributes
This mechanic has no attributes

## Examples
```yaml
CustomCompass:
  Id: COMPASS
  Skills:
  - setcompasslocation{} @Location{x=100;y=71;z=-120} ~onUse
```