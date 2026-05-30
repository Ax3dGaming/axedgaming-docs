# Getting Started

Scavenging recipes are loaded through Minecraft datapacks.

Recipes are stored in:

```text
data/<namespace>/recipe/
```

Example:

```text
data/scavenging/recipe/sand_scavenging.json
```

## Basic Recipe

```json
{
  "type": "scavenging:scavenging",
  "tool": {
    "item": "minecraft:stone_shovel"
  },
  "damage_tool": true,
  "block": "minecraft:sand",
  "outputs": [
    {
      "item": {
        "id": "minecraft:cobblestone",
        "count": 1
      },
      "chance": 0.75
    }
  ]
}
```

When the player right-clicks a sand block with a stone shovel, the recipe is executed.

The output has a 75% chance to drop.
