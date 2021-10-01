---
title: Predicate
date: 2021-04-04
---
# Predicate

[Entity Condition](../entity_conditions.md).

Checks whether the entity fulfills a certain [predicate](https://minecraft.gamepedia.com/Predicate).

**Note:** this condition is only effective on the server-side. That means client-based power types such as [`origins:climbing`](../power_types/climbing.md), [`origins:entity_glow`](../power_types/entity_glow.md), [`origins:shader`](../power_types/shader.md), etc. won't work with this.

Type ID: `origins:predicate`

### Fields:

Field  | Type | Default | Description
-------|------|---------|-------------
`predicate` | [Identifier](../data_types/identifier.md) | |  ID of the predicate the entity needs to pass.

### Example:
```json
"condition": {
    "type": "origins:predicate",
    "predicate": "example:weather/is_thunderstorm"
}
```
This example checks if the `test:check_if_thunderstorm` predicate (`data\example\predicates\weather\is_thunderstorm.json`) is true.


```json
{
    "condition": "minecraft:weather_check",
    "raining": true,
    "thundering": true
}
```
This being the contents of the `example:check_if_thunderstorm` predicate. (`data\example\predicates\weather\is_thunderstorm.json`)