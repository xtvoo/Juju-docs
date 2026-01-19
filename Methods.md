# 📚 Juju API Methods

**Status:** Auto-generated from Juju Dump
**Namespace:** `juju`

## 🚀 Core API

### UI & System
Methods for creating and managing the user interface.

| Method | Description |
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

### Configuration
| Method | Description |
| :--- | :--- |
| `juju.get_flag(flag_name)` | Returns the value of a flag (boolean, number, string). |
| `juju.set_flag(flag_name, value)` | Sets the value of a flag. |
| `juju.get_flags()` | Returns a table of all flags and their values. |

## 🎮 Game Interaction

### Player & World
| Method | Description |
| :--- | :--- |
| `juju.is_player_knocked(player)` | Returns `true` if player is KO'd. |
| `juju.is_player_dead(player)` | Returns `true` if player is dead. |
| `juju.is_player_invulnerable(player)` | Returns `true` if player has FF/Godmode. |
| `juju.is_in_void()` | Returns `true` if local player is currently voiding. |
| `juju.is_in_vehicle()` | Returns `true` if local player is driving/sitting in a vehicle. |
| `juju.get_ping(player)` | Get a player's ping. |
| `juju.get_player_crew(player)` | Get a player's crew ID/Name. |
| `juju.get_player_status(player)` | Get custom status (e.g. "Whitelisted"). |
| `juju.set_player_status(player, status)` | Set custom status. |

### Actions
| Method | Description |
| :--- | :--- |
| `juju.is_auto_stomping()` | Returns `true` if auto-stomp is active. |
| `juju.is_purchasing()` | Returns `true` if a purchase macro is running. |
| `juju.purchase_item(item_name)` | Buys an item from a shop (teleports automatically). |
| `juju.reload_gun()` | Forces a reload action. |

## 📍 Movement & Position

| Method | Description |
| :--- | :--- |
| `juju.get_server_cframe(player)` | Get the *server-sided* position of a player (bypasses lag/desync). |
| `juju.set_server_cframe(cframe)` | Teleport local player on the server (Voiding/TPs). |
| `juju.get_client_cframe(player)` | Get the client-sided position. |
| `juju.get_backtrack_position(player)` | Get the position used for backtracking. |

## ⚔️ Ragebot & Aimbot

| Method | Description |
| :--- | :--- |
| `juju.get_active_ragebot_target()` | Returns the current target player. |
| `juju.set_active_ragebot_target(player)` | Force the ragebot to target a specific player. |
| `juju.add_ragebot_target(player)` | Whitelist/Prioritize a player. |
| `juju.remove_ragebot_target(player)` | Remove from priority. |
| `juju.get_ragebot_targets()` | Get list of potential targets. |
| `juju.is_ragebot_target(player)` | Checks if player is a valid target. |
| `juju.get_ragebot_aim_position()` | Get the Vector3 where the aimbot is locking. |
| `juju.set_ragebot_aim_position(vec3)` | Override aim position. |
| `juju.get_silent_aim_position()` | Get silent aim target coordinate. |
| `juju.set_silent_aim_position(vec3)` | Override silent aim target. |
| `juju.set_aim_assist_position(vec3)` | Override aim assist target. |
| `juju.get_legitbot_target()` | Get current legitbot target. |
| `juju.set_legitbot_target(player)` | Set legitbot target. |

## 🛠️ Utility

| Method | Description |
| :--- | :--- |
| `juju.get_active_keybinds()` | Get currently pressed keybinds. |
| `juju.get_all_keybinds()` | Get configuration of all bound keys. |
| `juju.get_signal(name)` | Get a specific signal object. |
| `juju.get_signals()` | Get all available signals. |
| `juju.add_control_command(cmd)` | Add a chat command? |
| `juju.remove_control_command(cmd)` | Remove a chat command. |
