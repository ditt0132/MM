Updates the item on MM reload when ItemVersion differs.
This allows you to update items when MM reloads by changing the ItemVersion. If you haven't reset your config.yml in a while, then this feature requires the following to be added to the MythicCrucible config.yml:

```yml
ItemUpdater:
  Enabled: true
```

Below are a couple examples:

```yml
yet_another_example_item:
  Id: diamond_sword
  ItemVersion: 1
  Lore:
    - "Really really cool sword."
```

```yml
yet_another_example_item:
  Id: diamond_sword
  ItemVersion: 2
  Lore:
    - "I hated the old lore so I updated it."
```

The second sword will replace the first sword with the updated lore whenever a player interacts with it in their inventory.