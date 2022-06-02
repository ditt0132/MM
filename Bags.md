Custom Bags
-----------

Crucible allows you to create custom bags. 
Creating a bag is simple, all you need to do is give the Crucible Item a `BAG` type.

```yml
BAG_TEST:
  Id: paper
  Type: BAG
  Inventory:
    Title:
    Size:
```

### Bag Options

- `Title` - inventory title of your custom bag. Defaults to the display name of your Crucible item.
- `Size` - the inventory size of your custom bag. Size is limited to 9,18,27,36,45, and 54.

### Bag Mechanics

| Mechanics     | Description             |
|---------------|-------------------------|
| OpenInventory | Opens the bag inventory |