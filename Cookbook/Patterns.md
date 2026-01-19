# 👨‍🍳 Juju scripting Cookbook

Common patterns and snippets for Juju scripting.

## Sticky Glue (Target Follow)
This snippet demonstrates how to "glue" your character to the current Ragebot target using engine properties.

```lua
-- Loop or Signal based
local Target = juju.get_active_ragebot_target()
if Target and Target.Character then
    -- Hard stick using hidden engine property
    sethiddenproperty(LocalPlayer.Character.HumanoidRootPart, "PhysicsRepRootPart", Target.Character.HumanoidRootPart)
end
```

## Signal Listener Pattern
How to properly connect to Juju's internal signals and clean them up.

```lua
local valid_connection = juju.create_connection(juju.get_signal("on_ragebot_target_changed"), function(target_name)
    print("New Target:", target_name)
    -- Update glue target here
end)

-- Always clean up connections when your script unloads
juju.on_unload(function()
    valid_connection:Disconnect() 
end)
```
