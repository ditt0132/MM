Condition: custommodeldata
===

Description
---
Tests the custom model data of the item that executed the skill


Attributes
---

| Attribute | Aliases |            Description             | Default Value |
|:---------:|:-------:|:----------------------------------:|:-------------:|
|   model   |    m    | The custom model data to check for |       0       |

Examples
---

```yml
CUSTOM_SKILL:
  Conditions:
    - custommodeldata{m=1} true
```

```yml
INLINE_EXAMPLE:
  Id: STICK
  Skills:
    - message{m=test} @self ~onSwing ?custommodeldata{m=1}
```