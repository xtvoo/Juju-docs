# Juju API Documentation

**Generated:** 2026-01-18
**Based on:** Runtime Dumps & Script Analysis (Updated with Remote Scan)

## 1. Global Functions

### Core UI & System
| Function | Description |
| :--- | :--- |
| `juju.create_tab(name)` | Create a new tab in the menu. |
| `juju.create_section(name, side, size, offset)` | Create a section. **Note:** `side` is the 2nd argument (1=Left, 2=Right). |
| `juju.create_element(section, options, config)` | Create toggles, sliders, buttons, etc. |
| `juju.create_notification(text, type, time)` | Show a popup notification. `type`: 1=Info/Success?, 2=Error? |
| `juju.create_connection(signal, callback)` | Connect to a signal. Returns a connection object. |
| `juju.on_unload(callback)` | Register a function to run when the script/cheat is unloaded. |
| `juju.load_config(config_name)` | Load a saved configuration. |
| `juju.find_element(name)` | Find a UI element instance. |
| `juju.set_tab_text(tab, text)` | Rename a tab dynamically. |

### Configuration (Flags)
| Function | Description |
| :--- | :--- |
| `juju.get_flag(flag_name)` | Returns the value of a flag (boolean, number, string). |
| `juju.set_flag(flag_name, value)` | Sets the value of a flag. |
| `juju.get_flags()` | Returns a table of all flags and their values. |

### Da Hood / Game Interaction
| Function | Description |
| :--- | :--- |
| `juju.is_player_knocked(player)` | Returns `true` if player is KO'd. |
| `juju.is_player_dead(player)` | Returns `true` if player is dead. |
| `juju.is_player_invulnerable(player)` | Returns `true` if player has FF/Godmode. |
| `juju.is_in_void()` | Returns `true` if local player is currently voiding. |
| `juju.is_in_vehicle()` | Returns `true` if local player is driving/sitting in a vehicle. |
| `juju.is_auto_stomping()` | Returns `true` if auto-stomp is active. |
| `juju.is_purchasing()` | Returns `true` if a purchase macro is running. |
| `juju.purchase_item(item_name)` | Buys an item from a shop (teleports automatically). |
| `juju.reload_gun()` | Forces a reload action. |
| `juju.get_ping(player)` | Get a player's ping. |
| `juju.get_player_crew(player)` | Get a player's crew ID/Name. |
| `juju.get_player_status(player)` | Get custom status (e.g. "Whitelisted"). |
| `juju.set_player_status(player, status)` | Set custom status. |

### Movement & Position
| Function | Description |
| :--- | :--- |
| `juju.get_server_cframe(player)` | Get the *server-sided* position of a player (bypasses lag/desync). |
| `juju.set_server_cframe(cframe)` | Teleport local player on the server (Voiding/TPs). |
| `juju.get_client_cframe(player)` | Get the client-sided position. |
| `juju.get_backtrack_position(player)` | Get the position used for backtracking. |

### Aimbot & Ragebot
| Function | Description |
| :--- | :--- |
| `juju.get_active_ragebot_target()` | Returns the current target player. |
| `juju.set_active_ragebot_target(player)` | Force the ragebot to target a specific player. |
| `juju.add_ragebot_target(player)` | Whitelist/Prioritize a player? |
| `juju.remove_ragebot_target(player)` | Remove from priority? |
| `juju.get_ragebot_targets()` | Get list of potential targets. |
| `juju.is_ragebot_target(player)` | Checks if player is a valid target. |
| `juju.get_ragebot_aim_position()` | Get the Vector3 where the aimbot is locking. |
| `juju.set_ragebot_aim_position(vec3)` | Override aim position. |
| `juju.get_silent_aim_position()` | Get silent aim target coordinate. |
| `juju.set_silent_aim_position(vec3)` | Override silent aim target. |
| `juju.get_legitbot_target()` | Get current legitbot target. |
| `juju.set_legitbot_target(player)` | Set legitbot target. |

### Utility
| Function | Description |
| :--- | :--- |
| `juju.get_active_keybinds()` | Get currently pressed keybinds. |
| `juju.get_all_keybinds()` | Get configuration of all bound keys. |
| `juju.get_signal(name)` | Get a specific signal object. |
| `juju.get_signals()` | Get all available signals. |
| `juju.add_control_command(cmd)` | Add a chat command? |
| `juju.remove_control_command(cmd)` | Remove a chat command. |

---

## 2. Signals
Connect to these using `juju.create_connection(juju.get_signal("SignalName"), callback)`.

| Signal | Description |
| :--- | :--- |
| **Combat** | |
| `on_shot_at` | Fired when someone shoots at you. |
| `on_player_bullet_fired` | Fired when any player shoots (contains Origin, Direction data). |
| `on_local_bullet_fired` | Fired when YOU shoot. |
| `on_local_bullet_confirmed` | Your shot hit a player (server confirmed). |
| `on_local_bullet_failed` | Your shot missed or was rejected. |
| `on_rpg_fired` | RPG usage detected. |
| `on_player_died` | Player death event. |
| `on_player_knocked` | Player KO event. |
| `on_local_knocked` | You were KO'd. |
| `on_stomp` | Stomp execution event. |
| **State** | |
| `on_player_health_changed` | HP update (useful for health-based logic). |
| `on_local_health_changed` | Your HP update. |
| `on_player_armor_changed` | Armor update. |
| `on_local_armor_changed` | Your armor update. |
| `on_local_ammo_changed` | Ammo count update. |
| `on_local_reload` | You reloaded. |
| `on_local_tool_equipped` | You equipped an item. |
| `on_player_tool_equipped` | Enemy equipped an item. |
| **World/Player** | |
| `on_player_added` | Player joined server. |
| `on_player_character_added` | Player character spawned. |
| `on_vehicle_sat_in` | Entered a car. |
| **Aimbot** | |
| `on_ragebot_target_changed` | Target switch event (crucial for "Sticky" scripts). |
| `on_legitbot_target_changed` | Legitbot target switch event. |

---

## 3. Key Flags (Configuration)
Use `juju.set_flag(flag, value)` to control these features.

### Ragebot & Aimbot
*   `ragebot` (bool): Master switch.
*   `silent_aim` (bool)
*   `auto_fire` (bool)
*   `resolver` (bool): Anti-aim revolver.
*   `backtrack` (bool): Backtrack enabled.
*   `backtrack_length` (number): Time in ms (e.g. 200).
*   `rapid_fire` (bool)
*   `anti_sit` (bool): Prevent sitting?
*   `target_selection_use_player_list` (bool)

### Anti-Aim & Exploits
*   `spinbot` (bool)
*   `spinbot_speed` (number)
*   `fake_position` (bool): Desync/Fake lag.
*   `noclip` (bool)
*   `flight` (bool)
*   `speed` (bool)
*   `speed_value` (number)
*   `anti_stomp` (bool): Prevent being stomped?
*   `anti_bag` (bool): Prevent being bagged.

### Void Exploits
*   `void_spam_enabled` (bool)
*   `void_spam_pattern` (string)
*   `void_method` (string)
*   `void_assist_method` (string)
*   `void_stay_invuln` (bool): Don't void if enemy is in godmode.
*   `void_stay_knocked` (bool): Don't void if enemy is KO.
*   `void_stay_low_hp` (bool)

### Visuals (ESP)
*   `esp` (bool)
*   `box` (bool)
*   `name` (bool)
*   `health_bar` (bool)
*   `armor_bar` (bool)
*   `chams` (bool)
*   `tracers` (bool)
*   `highlight` (bool)

### Automation
*   `auto_buy_armor` (bool)
*   `auto_buy_ammo` (bool)
*   `auto_reload` (bool)
*   `auto_heal` (bool)
*   `auto_stomp` (bool): Master switch for built-in auto stomp.
*   `trash_talk` (bool)

## 5. Da Hood Internals (Remotes)
**Discovered via `ReplicatedStorage` scan.**

### Core Remotes
| Remote Name | Parent | Type | Notes |
| :--- | :--- | :--- | :--- |
| `MainEvent` | `ReplicatedStorage` | RemoteEvent | **The "Shoot Remote"**. Handles combat, stomps, etc. |
| `MainRemoteFunction` | `ReplicatedStorage` | RemoteFunction | Data fetching. |
| `Network` | `Remotes` | RemoteEvent | General networking. |
| `Handshake` | `Remotes` | RemoteEvent | Anti-cheat/Auth handshake? |
| `PurchasePrompt` | `Remotes` | RemoteEvent | Item buying interface. |
| `SetBounty` | `Remotes` | RemoteFunction | Setting bounties. |

### Event/Misc Remotes
| Remote Name | Parent | Type |
| :--- | :--- | :--- |
| `TapBall` | `Remotes` | RemoteEvent | soccer/ball minigame? |
| `MacroDisableVote` | `Remotes` | RemoteEvent | |
| `ToggleLeaderboardVisibility` | `Remotes` | RemoteEvent | |
| `IronmanSuit` | `Events` | RemoteEvent | Possibly admin/special event. |
| `Luffy` | `Remotes` | RemoteEvent | |

### Global Environment (`getgenv`)
*   `_JUJU`: Likely the internal table for configuration or state.
*   `_OG`: Original functions backup?

---

## 6. Scripting Patterns (Confirmed)
*(From previous analysis)*

### Sticky Glue (Target Follow)
```lua
local Target = juju.get_active_ragebot_target()
if Target and Target.Character then
    -- Hard stick using engine property
    sethiddenproperty(LocalPlayer.Character.HumanoidRootPart, "PhysicsRepRootPart", Target.Character.HumanoidRootPart)
end
```

### Signal Listener Pattern
```lua
local valid_connection = juju.create_connection(juju.get_signal("on_ragebot_target_changed"), function(target_name)
    print("New Target:", target_name)
    -- Update glue target here
end)

juju.on_unload(function()
    valid_connection:Disconnect() -- Wrapper likely handles this, but good practice
end)
```
