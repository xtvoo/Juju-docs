# 🏥 Da Hood Internals

**Discovered via:** Recursive Remote Scanning
**Status:** Confirmed Active

## ⚡ Core Remotes
These rely on standard Roblox networking and can be manipulated for advanced features.

| Remote Name | Parent | Type | Notes |
| :--- | :--- | :--- | :--- |
| `MainEvent` | `ReplicatedStorage` | RemoteEvent | **The "Shoot Remote"**. Handles combat, stomps, etc. |
| `MainRemoteFunction` | `ReplicatedStorage` | RemoteFunction | Data fetching. |
| `Network` | `Remotes` | RemoteEvent | General networking. |
| `Handshake` | `Remotes` | RemoteEvent | Anti-cheat/Auth handshake? |
| `PurchasePrompt` | `Remotes` | RemoteEvent | Item buying interface. |
| `SetBounty` | `Remotes` | RemoteFunction | Setting bounties. |

## 🛠️ Misc Remotes

| Remote Name | Parent | Type | Description |
| :--- | :--- | :--- | :--- |
| `TapBall` | `Remotes` | RemoteEvent | soccer/ball minigame? |
| `MacroDisableVote` | `Remotes` | RemoteEvent | Voting system. |
| `ToggleLeaderboardVisibility` | `Remotes` | RemoteEvent | UI Toggle. |
| `IronmanSuit` | `Events` | RemoteEvent | Possibly admin/special event. |
| `Luffy` | `Remotes` | RemoteEvent | Special event? |
| `CasinoVisuals` | `Remotes` | RemoteEvent | Casino effects. |
| `CasinoRR` | `Remotes` | RemoteFunction | Casino logic. |
| `LightSwordRemote` | `Remotes` | RemoteEvent | Star Wars event? |
| `Replication` | `Events` | RemoteEvent | Character/State replication. |
| `PacketReceiver` | `Events` | RemoteEvent | Network packet handling. |
| `Logging` | `ReplicatedStorage` | RemoteEvent | Anti-cheat/Error logging. |

## 🌍 Global Environment (`getgenv`)
*   `_JUJU`: Internal table for configuration or state.
*   `_OG`: Original functions backup.
