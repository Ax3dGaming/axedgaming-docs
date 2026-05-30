# Recipe Format

## Root Fields

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| type | String | Yes | Must be `scavenging:scavenging` |
| block | String | Yes | Block to scavenge |
| outputs | Array | Yes | Loot outputs |
| tool | Object | No | Required tool |
| requires_empty_hand | Boolean | No | Recipe requires an empty hand |
| damage_tool | Boolean | No | Consumes 1 durability when executed |

## Basic Recipe

=== "JSON"

    ```json
    {
      "type": "scavenging:scavenging",
      "tool": {
        "item": "minecraft:stone_shovel"
      },
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

=== "KubeJS"

    ```js
    ServerEvents.recipes(event => {
      event.recipes.scavenging.scavenging(
        'minecraft:sand',
        [
          {
            item: 'minecraft:cobblestone',
            chance: 0.75
          }
        ]
      ).tool('minecraft:stone_shovel')
    })
    ```

=== "KubeJS JSON"

    ```js
    ServerEvents.recipes(event => {
      event.custom({
        type: 'scavenging:scavenging',
        tool: {
          item: 'minecraft:stone_shovel'
        },
        block: 'minecraft:sand',
        outputs: [
          {
            item: {
              id: 'minecraft:cobblestone',
              count: 1
            },
            chance: 0.75
          }
        ]
      })
    })
    ```

## Bare Hand Recipe

=== "JSON"

    ```json
    {
      "type": "scavenging:scavenging",
      "requires_empty_hand": true,
      "block": "minecraft:dirt",
      "outputs": [
        {
          "item": {
            "id": "minecraft:stick",
            "count": 1
          },
          "chance": 0.25
        }
      ]
    }
    ```

=== "KubeJS"

    ```js
    ServerEvents.recipes(event => {
      event.recipes.scavenging.scavenging(
        'minecraft:dirt',
        [
          {
            item: 'minecraft:stick',
            chance: 0.25
          }
        ]
      ).requiresEmptyHand(true)
    })
    ```

=== "KubeJS JSON"

    ```js
    ServerEvents.recipes(event => {
      event.custom({
        type: 'scavenging:scavenging',
        requires_empty_hand: true,
        block: 'minecraft:dirt',
        outputs: [
          {
            item: {
              id: 'minecraft:stick',
              count: 1
            },
            chance: 0.25
          }
        ]
      })
    })
    ```

## Multiple Outputs

=== "JSON"

    ```json
    {
      "type": "scavenging:scavenging",
      "tool": {
        "item": "minecraft:stone_shovel"
      },
      "block": "minecraft:sand",
      "outputs": [
        {
          "item": {
            "id": "minecraft:cobblestone",
            "count": 1
          },
          "chance": 1.0
        },
        {
          "item": {
            "id": "minecraft:flint",
            "count": 1
          },
          "chance": 0.25
        },
        {
          "item": {
            "id": "minecraft:diamond",
            "count": 1
          },
          "chance": 0.01
        }
      ]
    }
    ```

=== "KubeJS"

    ```js
    ServerEvents.recipes(event => {
      event.recipes.scavenging.scavenging(
        'minecraft:sand',
        [
          {
            item: 'minecraft:cobblestone',
            chance: 1.0
          },
          {
            item: 'minecraft:flint',
            chance: 0.25
          },
          {
            item: 'minecraft:diamond',
            chance: 0.01
          }
        ]
      ).tool('minecraft:stone_shovel')
    })
    ```

=== "KubeJS JSON"

    ```js
    ServerEvents.recipes(event => {
      event.custom({
        type: 'scavenging:scavenging',
        tool: {
          item: 'minecraft:stone_shovel'
        },
        block: 'minecraft:sand',
        outputs: [
          {
            item: {
              id: 'minecraft:cobblestone',
              count: 1
            },
            chance: 1.0
          },
          {
            item: {
              id: 'minecraft:flint',
              count: 1
            },
            chance: 0.25
          },
          {
            item: {
              id: 'minecraft:diamond',
              count: 1
            },
            chance: 0.01
          }
        ]
      })
    })
    ```

Each output is rolled independently.