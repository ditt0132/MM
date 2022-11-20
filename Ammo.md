Crucible adds a simple ammo system to allow you to easily create guns that use other items as ammunition. 

Configuring an Item
-------------------
The ammo system has its own configuration block on an item:
```
TestGun:
  Ammo:
    Enabled: TRUE
    Bullet: TestAmmo
    ClipSize: 10
    AmmoPerItem: 1
```

| Attribute | Description |
|-----------|-------------|
| Enabled   | Set true to enable ammo usage on the item |
| Bullet    | The name of the item to use as a "bullet" when reloading |
| ClipSize  | The maximum amount of ammo the item can hold at once |
| AmmoPerItem | How much ammo each bullet will add when consumed |
| ConsumeOnUse | Whether or not the `~onUse` trigger will automatically require and consume ammo, instead of using the `consumeAmmo` mechanic |

Items can also be configured to display ammunition in the item's lore. This is done by configurating a regex string in Crucible's configuration file that will be matched as what shows the ammo, and the matched group with the "current" number will update accordingly.

Using Ammunition
----------------
Ammo is used by calling the [AmmoConsume](Skills/Mechanics/AmmoConsume) mechanic. In the mechanic you specify how much ammo is needed, and if the item has that much ammo it will be consumed and the given skill will be executed.

Reloading Ammo
--------------
Reloading ammo is done using the [AmmoReload](Skills/Mechanics/AmmoReload) mechanic. Calling it will search the caster's inventory for the configured ammo item (or another item if overridden), and for each item it finds it will consume it and add ammo to the item.

Example Item
------------

Configured in an item file:
```
TestGun:
  Id: BLAZE_ROD
  Model: 10
  Display: '<purple>X-97 Testing Phaser'
  Ammo:
    Enabled: TRUE
    ConsumeOnUse: true
    Bullet: TestAmmo
    ClipSize: 10
    AmmoPerItem: 1
  Lore:
  - "&7Ammunition 10 / 10"
  Skills:
   - consumeammo{amount=1; onNoAmmo=TestGun-OutOfAmmo; onUse=TestGun-Fire} @self ~onUse
  - reloadammo{sync=false;
      onReload=TestGun-Reload;
      onFail=TestGun-Reload-Fail;
      onFull=TestGun-Reload-Full} @self ~onSwing
```

In a skills file:
```
TestGun-OutOfAmmo:
  Skills:
  - am{m="&c&lOut of Ammo"}

TestGun-Fire:
  Skills:
  - raytrace{
      origin=@forward{a=1;y=1};
      entitySkill=TestGun-Damage;
      locationSkill=TestGun-Fire-Effect}
  - recoil{r=0.2;yawMod=-2to2;repeat=1;repeati=4} @self

TestGun-Damage:
  Skills:
  - damage{amount=10}
  
TestGun-Fire-Effect:
  Skills:
  - sound{s=block.conduit.activate;p=1.75;v=1} @origin
  - particleline{p=mobSpell;color=#FFFFFF;db=2;
        fO=true;origin=@MuzzleLocation{y=-0.2};audience=SELF}
  - particleline{p=mobSpell;color=#FFFFFF;db=2;fromOrigin=true;audience=NONSELF}

TestGun-Reload:
  Skills:
  - actionmessage{m="&e&lRELOADING"} @self
  - potion{type=SLOW_DIGGING;level=20;d=40}
  - delay 1
  - playanimation{audience=SELF;animation=0} @self
  - delay 40
  - potion{type=FAST_DIGGING;level=99}

TestGun-Reload-Fail:
  Skills:
  - actionmessage{m="&4&lOUT OF AMMO"} @self
  - sound{s=item.flintandsteel.use;p=.1}

TestGun-Reload-Full:
  Skills:
  - actionmessage{m="&e&oAMMO FULL"} @self
  - sound{s=item.flintandsteel.use;p=.1}
```