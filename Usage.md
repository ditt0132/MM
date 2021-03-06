Item Creation
-------------
Crucible is an add-on for MythicMobs, and uses the same existing item system. This means that you simply add the additional configs to items that you've already made in your MythicMobs folder.

**Crucible does not have its own Items folder.**

Skills are added to items in a **Skills:** block, using the exact same syntax as mob skills.

For example, this item would draw a line of fire to the location you're looking at when you right-click:
```
SpecialSword:
  Id: DIAMOND_SWORD
  Display: '&6A Sword with a Skill'
  Skills:
  - effect:particleline{p=flame} @targetlocation ~onUse
```
Most mechanics and conditions from MythicMobs can be used on items - almost anything that makes sense will work how you'd expect. Crucible also supports most skill triggers, and also adds a bunch of new skill triggers, for activating your skills.

You can read more about the new toys Crucible adds for skills in the manual:

### New Mechanics
  * [Item Mechanics](Skills/Mechanics)
  * [Item Targeters](Skills/Targeters)
  * [Item Triggers](Skills/Triggers)
  * [Item Conditions](Skills/Conditions)
### Special Features
  * [Ammo System / Making Guns](Ammo)
  * [Special Options](Options)