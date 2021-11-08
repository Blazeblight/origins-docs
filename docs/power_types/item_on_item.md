---
title: Item On Item (Power Type)
date: 2021-10-02
---

# Item On Item

[Power Type](../power_types.md)

Executes an entity action or item actions on the item used for right-clicking an item, or the item that's been right-clicked when the player uses an item on an item (e.g: right-clicking an item on top of an item, like how you would put items in a bundle).

Type ID: `origins:item_on_item`

!!! caution

    This power type currently does not work properly in Creative Mode.

### Fields

Field | Type | Default | Description
------|------|---------|-------------
`using_item_condition` | [Item Condition](../item_conditions.md) | _optional_ | If set, the actions will only trigger when this condition is met by the item used to right-click an item stack.
`on_item_condition` | [Item Condition](../item_conditions.md) | _optional_ | If set, the actions will only trigger when this condition is met by the item stack that's been right-clicked.
`result` | [Item Stack](../data_types/item_stack.md) | _optional_ | If set, the specified item stack will be given to the player.
`using_item_action` | [Item Action](../item_actions.md) | _optional_ | If set, this action will be executed on the item stack used to right-click an item stack.
`on_item_action` | [Item Action](../item_actions.md) | _optional_ | If set, this action will be executed on the item stack that's been right-clicked.
`result_item_action` | [Item Action](../item_actions.md) | _optional_ | If set, this action will be executed on the item stack specified in the `result` field.
`entity_action` | [Entity Action](../entity_actions.md) | _optional_ | If set, this action will be executed on the player after they used an item on an item.

### Example
```json
{
    "type": "origins:item_on_item",
    "using_item_condition": {
        "type": "origins:ingredient",
        "ingredient": {
            "tag": "fabric:axes"
        }
    },
    "on_item_condition": {
        "type": "origins:ingredient",
        "ingredient": {
            "item": "minecraft:oak_log"
        }
    },
    "result": {
        "item": "minecraft:oak_planks",
        "amount": 8
    },
    "using_item_action": {
        "type": "origins:damage",
        "amount": 20,
        "ignore_unbreaking": false
    },
    "on_item_action": {
        "type": "origins:consume",
        "amount": 1
    },
    "entity_action": {
        "type": "origins:play_sound",
        "sound": "minecraft:entity.zombie.break_wooden_door",
        "volume": 0.45,
        "pitch": 2
    }
}
```
This example will give the player 8 Oak Planks if the player were to use any Axe tool item on an Oak Log item (have the Axe tool item in the cursor, and right-click on an Oak Log item). 