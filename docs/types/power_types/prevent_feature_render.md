---
title: Prevent Feature Render
date: 2021-12-04
---

# Prevent Feature Render

[Power Type](../power_types.md)

Prevents certain feature renderers (e.g: armor layer, sheep wool layer, or the sub-classes that extends the [`FeatureRender`](https://maven.fabricmc.net/docs/yarn-1.18+build.1/net/minecraft/client/render/entity/feature/FeatureRenderer.html) super-class) from rendering to the entity that has this power.

Type ID: `origins:prevent_feature_render`

!!! note

    The sub-classes that extends the `FeatureRender` super-class uses pascal-case for its class name. One can convert it to snake-case and remove the `*FeatureRenderer` prefix, which will then be the string value that can be used in the `feature` or `features` fields of the power type.

    (e.g: `ArmorFeatureRenderer` --> `"armor"`, `HeldItemFeatureRenderer` --> `"held_item"`, etc.) 


### Fields

Field | Type | Default | Description
------|------|---------|------------
`feature` | [String](../data_types/string.md) | _optional_ | If specified, this feature renderer will not be rendered.
`features` | [Array](../data_types/array.md) of [Strings](../data_types/string.md) | _optional_ | If specified, these feature renderers will not be rendered.


### Examples

```json
{
    "type": "origins:prevent_feature_render",
    "features": [
        "armor",
        "held_item",
        "elytra"
    ]
}
```

This example will make the armor layer, held item and worn Elytra essentially invisible for other players.