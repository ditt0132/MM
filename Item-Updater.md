Updates the item on MM reload when ItemVersion differs.
This allows you to update items when MM reloads by changing the ItemVersion. Inside your `config.yml` you will find the following option to determine if this feature should be available or not:
```yml
ItemUpdater:
  Enabled: true
```

And enabling that allows for the following options to be used inside items:
```yaml
example_item:
  Id: stone
  ItemUpdater:
    Version: 0                # Defaults at 0
    PreserveStatRatio: true   # Defaults at true
```

## Examples
```yml
yet_another_example_item:
  Id: diamond_sword
  ItemUpdater:
    Version: 1
    PreserveStatRatio: true
  Lore:
    - "Really really cool sword."
```

```yml
yet_another_example_item:
  Id: diamond_sword
  ItemUpdater:
    Version: 2
    PreserveStatRatio: true
  Lore:
    - "I hated the old lore so I updated it."
```

The second sword will replace the first sword with the updated lore whenever a player interacts with it in their inventory.