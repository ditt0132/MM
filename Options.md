These options are applicable to all items, and go under the Options field:

| Option                       | Description                                                    |
|------------------------------|----------------------------------------------------------------|
| CancelDamage: [true/false]   | Prevents the item from doing physical damage on melee hit.     |
| Destroy: [true/false]        | If true, the item will be removed from every player. Used to remove a matching item from the server. |
| DestroyOnDrop: [true/false]  | Destroys the item if the player drops it.                      |
| KeepOnDeath: [true/false]    | Players won't drop the item on death.                          |
| PreventDropping: [number]    | Prevents the item from being dropped.                          |
| Permission: [perm.node]      | Required perm node to have this item. If the player doesn't have the permission, it will be removed from their inventory when they attempt to use it (use permission conditions in skills if you just want to prevent skill usage).