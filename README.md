Basic bundle for having vendor NPCs. Adds a `shop` command players can use to to
buy and sell items.

## Creating a vendor

```yaml
- id: wallythewonderful
  name: "Wally the Wonderful"
  description: >-
   Wally's Shop has the best wares in town! Armor, weapons and potions, you name and we ... might have it!
  behaviors:
    # use the 'vendor' behavior to make an NPC a vendor
    vendor:
      // The 'items' config specifies the items they have for sale
      items:
        # each entry is the entityReference of the item along with the cost
        # and which currency to use for the cost
        "limbo:trainingsword":
          cost: 30
          currency: gold
        "limbo:leathervest":
          cost: 30
          currency: gold
        "limbo:woodenshield":
          cost: 30
          currency: gold
        "limbo:potionhealth1":
          cost: 100
          currency: gold
        "limbo:potionstrength1":
          cost: 150
          currency: gold
        "limbo:bladeofranvier":
          cost: 99999
          currency: gold
```

Vendors have an infinite supply, each purchased item will be generated
on-demand.

## Making an item sellable

Items can only be sold to a vendor if they have the `sellable` behavior

```yaml
- id: "scraps"
  name: "Scraps"
  behaviors:
    sellable:
      value: 5
      currency: gold
```

Sold items are removed from the game.
