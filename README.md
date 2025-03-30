# How to Install Mods for this Server

To join this server, you need to install specific mods. The easiest way is using a mod manager.

## Method 1: Using a Mod Manager (Recommended)

Using **r2modman** or **Thunderstore Mod Manager** is highly recommended.

1.  **Install Manager:** Download and install r2modman or Thunderstore Mod Manager.
2.  **Select Valheim:** Launch the manager and select Valheim.
3.  **Create Profile:** Create a new profile (e.g., "Albear Server").
4.  **Install Mods:** Go to "Online" or "Get Mods" and install the mods listed below using the provided links or by searching. Dependencies like BepInEx and Jotunn will usually be installed automatically.
5.  **Launch:** **Always** start the game using the "Start Modded" button in the mod manager.

## Method 2: Manual Installation

1.  **Install BepInEx:** Download `BepInExPack_Valheim` from [here](https://valheim.thunderstore.io/package/denikson/BepInExPack_Valheim/) and extract its contents into your main Valheim game folder (`steamapps/common/Valheim`).
2.  **Install Jotunn:** Download `ValheimModding-Jotunn` from [here](https://valheim.thunderstore.io/package/ValheimModding/Jotunn/) and extract its `.dll` into `Valheim/BepInEx/plugins`.
3.  **Download & Install Required Mods:** Download each mod from the list below and extract their `.dll` files (and any other included files/folders) into your `Valheim/BepInEx/plugins` folder.
4.  **Launch:** Start Valheim through Steam.

## Required Client-Side Mods

You **must** install these mods (and their dependencies like BepInEx/Jotunn) to join:

*   **CheatDeath:** [Link](https://thunderstore.io/c/valheim/p/shudnal/CheatDeath/)
*   **ServerCharacters:** [Link](https://thunderstore.io/c/valheim/p/Smoothbrain/ServerCharacters/)
*   **VentureFloatingItems:** [Link](https://thunderstore.io/c/valheim/p/VentureValheim/Venture_Floating_Items/)
*   **VentureLogoutTweaks:** [Link](https://thunderstore.io/c/valheim/p/VentureValheim/Venture_Logout_Tweaks/) (Link assumed based on other mods by author)
*   **VentureMultiplayerTweaks:** [Link](https://thunderstore.io/c/valheim/p/VentureValheim/Venture_Multiplayer_Tweaks/)
*   **WardIsLove:** [Link](https://thunderstore.io/c/valheim/p/Azumatt/WardIsLove/)
*   **WorldAdvancementProgression:** [Link](https://thunderstore.io/c/valheim/p/VentureValheim/World_Advancement_Progression/)

*(Note: `LocationReset` is likely server-side only and does not need to be installed by clients).*

---

# Valheim Modded Server Configuration Summary

This document outlines the major gameplay changes implemented through mod configurations, focusing on differences from vanilla Valheim.

## Progression & World

*   **Player-Based Progression & Boss Unlocks (`WorldAdvancementProgression`):** Game progression (unlocking recipes, items, etc.) is tied to individual player boss kills. Boss summons are locked initially; Server Admins will manually unlock the ability to summon the next boss globally (using `setkey`) for everyone approximately **one real-world week** after the previous boss unlock. Many actions like crafting specific tiers, building, and using guardian powers remain locked until the required boss is defeated by the player. ([Link](https://thunderstore.io/c/valheim/p/VentureValheim/World_Advancement_Progression/))
*   **Location Reset (`LocationReset`):** Dungeons, camps, and other points of interest will automatically reset and repopulate after a set number of in-game days. ([Link](https://thunderstore.io/c/valheim/p/VentureValheim/Venture_Location_Reset/))
    *   Standard Reset: 30 days
    *   Plains Camps / Mistlands Dungeons: 45 days
    *   Hildir Locations / Ashlands Locations: 60 days
    *   Ocean Leviathans: 15 days
    *   Ashlands Lava Leviathans: 30 days
*   **Floating Items (`FloatingItems`):** All items dropped in water will float instead of sinking. ([Link](https://thunderstore.io/c/valheim/p/VentureValheim/Venture_Floating_Items/))

## Combat & Survival

*   **Cheat Death (`CheatDeath`):** Instead of dying immediately upon taking fatal damage, players receive a 3-second protective buff. ([Link](https://thunderstore.io/c/valheim/p/shudnal/CheatDeath/))
    *   Buff Effects: 75% damage resistance, 100% reduced fall damage, 100% reduced movement stamina cost, +10 HP/second regeneration, +100 carry weight.
    *   Cooldown: 30 minutes (real-time).
*   **No Skill Drain in Ward (`WardIsLove`):** Permitted players dying inside an active ward *do not* lose skill levels. ([Link](https://thunderstore.io/c/valheim/p/Azumatt/WardIsLove/))
*   **Ward Passive Regen (`WardIsLove`):** Permitted players slowly regenerate health (0.25 HP/sec) and stamina (0.5 Stamina/sec) while inside an active ward. ([Link](https://thunderstore.io/c/valheim/p/Azumatt/WardIsLove/))
*   **Poison Debuff (`ServerCharacters`):** The poison status effect is cleared upon logging out. ([Link](https://thunderstore.io/c/valheim/p/Smoothbrain/ServerCharacters/))

## Building & Crafting

*   **Ward Protection (`WardIsLove`):** ([Link](https://thunderstore.io/c/valheim/p/Azumatt/WardIsLove/))
    *   Player-built structures take 75% less damage while inside an active ward.
    *   Weather damage does not affect structures inside a ward.
    *   Wards, Portals, Guard Stones, Chests, and Iron items/structures are indestructible inside a ward.
*   **Infinite Fuel (`WardIsLove`):** Ovens, Baths, and many common fireplaces/torches (walltorch, sconce, groundtorch variants, braziers, fire pit, bonfire, hearth) do not consume fuel while inside an active ward. ([Link](https://thunderstore.io/c/valheim/p/Azumatt/WardIsLove/))
*   **Ward Crafting (`WardIsLove`):** Wards require no specific item to activate. ([Link](https://thunderstore.io/c/valheim/p/Azumatt/WardIsLove/))

## Multiplayer & Interaction

*   **PvP Always Enabled (`MultiplayerTweaks`):** PvP is always enabled server-wide, including inside wards. ([Link](https://thunderstore.io/c/valheim/p/VentureValheim/Venture_Multiplayer_Tweaks/))
*   **Call to Arms (`WardIsLove`):** When a non-permitted player enters an active ward, all permitted players inside are flagged for PvP (overriding PvE settings if necessary). ([Link](https://thunderstore.io/c/valheim/p/Azumatt/WardIsLove/))
*   **Single Character (`ServerCharacters`):** Players may only create and use one character on this server per account (Steam/Xbox ID). ([Link](https://thunderstore.io/c/valheim/p/Smoothbrain/ServerCharacters/))
*   **AFK Kick (`ServerCharacters`):** Players inactive for 30 minutes will be automatically kicked from the server. ([Link](https://thunderstore.io/c/valheim/p/Smoothbrain/ServerCharacters/))
*   **Map Changes (`MultiplayerTweaks`):** ([Link](https://thunderstore.io/c/valheim/p/VentureValheim/Venture_Multiplayer_Tweaks/))
    *   Player positions are hidden on the map.
    *   Map pins for Haldor, Hildir, and the Bog Witch are hidden. (Starting Temple remains).
*   **Valkyrie Intro (`MultiplayerTweaks`, `ServerCharacters`):** The initial Valkyrie intro sequence is disabled for new characters. ([Link 1](https://thunderstore.io/c/valheim/p/VentureValheim/Venture_Multiplayer_Tweaks/), [Link 2](https://thunderstore.io/c/valheim/p/Smoothbrain/ServerCharacters/))
*   **Ward Permissions (`WardIsLove`):** ([Link](https://thunderstore.io/c/valheim/p/Azumatt/WardIsLove/))
    *   Non-permitted players CAN interact with: Dropped Items, Item Stands, Portals (including teleporting through them), Pickables (berries, crops), Chests, Beehives, Map Tables, Ships.
    *   Non-permitted players CANNOT interact with: Doors, Crafting Stations, Smelters, Signs. (They also cannot auto-pickup items).
*   **Offline Raid Protection (`WardIsLove`):** Player bases within wards are protected from damage by non-permitted players *unless* at least 1 permitted player is currently online on the server. ([Link](https://thunderstore.io/c/valheim/p/Azumatt/WardIsLove/))

## Server Management

*   **Server-Side Characters (`ServerCharacters`):** Player character data is stored and managed by the server, including backups. ([Link](https://thunderstore.io/c/valheim/p/Smoothbrain/ServerCharacters/))
*   **Auto-Save (`ServerCharacters`):** Server performs an auto-save every 5 minutes. ([Link](https://thunderstore.io/c/valheim/p/Smoothbrain/ServerCharacters/))