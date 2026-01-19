# 📡 API Signals

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
| `on_bounty_placed` | Fired when a bounty is placed on a player. |
| **State** | |
| `on_player_health_changed` | HP update (useful for health-based logic). |
| `on_local_health_changed` | Your HP update. |
| `on_player_armor_changed` | Armor update. |
| `on_local_armor_changed` | Your armor update. |
| `on_local_ammo_changed` | Ammo count update. |
| `on_local_reload` | You reloaded. |
| `on_local_tool_equipped` | You equipped an item. |
| `on_player_tool_equipped` | Enemy equipped an item. |
| `on_local_character_loaded` | Local character fully loaded. |
| `on_local_character_description_changed` | Local appearance changed. |
| `on_theme_color_change` | UI theme color updated. |
| **World/Player** | |
| `on_player_added` | Player joined server. |
| `on_player_character_added` | Player character spawned. |
| `on_player_character_added_quick` | Fast spawn event? |
| `on_vehicle_sat_in` | Entered a car. |
| `on_player_crew_changed` | Player joined/left a crew. |
| `on_player_role_changed` | Player role changed (e.g. Police/Criminal). |
| `on_player_status_changed` | Custom status update. |
| **Aimbot** | |
| `on_ragebot_target_changed` | Target switch event (crucial for "Sticky" scripts). |
| `on_ragebot_target_added` | Target added to whitelist/priority. |
| `on_ragebot_target_removed` | Target removed from whitelist/priority. |
| `on_legitbot_target_changed` | Legitbot target switch event. |
