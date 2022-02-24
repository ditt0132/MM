Mechanic: AmmoConsume
================

Consumes ammo to execute a skill. This skill does not need a targeter.

Attributes
----------

| Attribute | Aliases      | Description                           | Default |
|-----------|--------------|---------------------------------------|---------|
| amount     | a | How many ammo is consumed | 1     |
| onConsume | onUse, Use, UseSkill | The skill to trigger on ammo consume | |
| onNoAmmo | noAmmoSkill, noAmmo | The skill to trigger when there's no ammo left | |

  

Examples
--------

      Skills:
      - ammoconsume{amount=1;onConsume=ConsumeMetaSkill;onNoAmmo=NoAmmoMetaSkill}