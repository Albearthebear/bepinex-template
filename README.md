# Valheim Modded Server Configuration Summary

This document outlines the major gameplay changes implemented through mod configurations, focusing on differences from vanilla Valheim.

## Progression & World

*   **Player-Based Progression (`WorldAdvancementProgression`):** Game progression (unlocking recipes, items, etc.) is tied to individual player boss kills, not global server keys. Many actions like crafting specific tiers, building, summoning bosses, and using guardian powers are locked until the required boss is defeated by the player.
*   **Location Reset (`LocationReset`):** Dungeons, camps, and other points of interest will automatically reset and repopulate after a set number of in-game days.
    *   Standard Reset: 30 days
    *   Plains Camps / Mistlands Dungeons: 45 days
    *   Hildir Locations / Ashlands Locations: 60 days
    *   Ocean Leviathans: 15 days
    *   Ashlands Lava Leviathans: 30 days
*   **Floating Items (`FloatingItems`):** All items dropped in water will float instead of sinking.

## Combat & Survival

*   **Cheat Death (`CheatDeath`):** Instead of dying immediately upon taking fatal damage, players receive a 3-second protective buff.
    *   Buff Effects: 75% damage resistance, 100% reduced fall damage, 100% reduced movement stamina cost, +10 HP/second regeneration, +100 carry weight.
    *   Cooldown: 30 minutes (real-time).
*   **No Skill Drain in Ward (`WardIsLove`):** Permitted players dying inside an active ward *do not* lose skill levels.
*   **Ward Passive Regen (`WardIsLove`):** Permitted players slowly regenerate health (0.25 HP/sec) and stamina (0.5 Stamina/sec) while inside an active ward.
*   **Poison Debuff (`ServerCharacters`):** The poison status effect is cleared upon logging out.

## Building & Crafting

*   **Ward Protection (`WardIsLove`):**
    *   Player-built structures take 75% less damage while inside an active ward.
    *   Weather damage does not affect structures inside a ward.
    *   Wards, Portals, Guard Stones, Chests, and Iron items/structures are indestructible inside a ward.
*   **Infinite Fuel (`WardIsLove`):** Ovens, Baths, and many common fireplaces/torches (walltorch, sconce, groundtorch variants, braziers, fire pit, bonfire, hearth) do not consume fuel while inside an active ward.
*   **Ward Crafting (`WardIsLove`):** Wards require no specific item to activate.

## Multiplayer & Interaction

*   **PvP Always Enabled (`MultiplayerTweaks`):** PvP is always enabled server-wide, including inside wards.
*   **Call to Arms (`WardIsLove`):** When a non-permitted player enters an active ward, all permitted players inside are flagged for PvP (overriding PvE settings if necessary).
*   **Single Character (`ServerCharacters`):** Players may only create and use one character on this server per account (Steam/Xbox ID).
*   **AFK Kick (`ServerCharacters`):** Players inactive for 30 minutes will be automatically kicked from the server.
*   **Map Changes (`MultiplayerTweaks`):**
    *   Player positions are hidden on the map.
    *   Map pins for Haldor, Hildir, and the Bog Witch are hidden. (Starting Temple remains).
*   **Valkyrie Intro (`MultiplayerTweaks`, `ServerCharacters`):** The initial Valkyrie intro sequence is disabled for new characters.
*   **Ward Permissions (`WardIsLove`):**
    *   Non-permitted players CAN interact with: Dropped Items, Item Stands, Portals (including teleporting through them), Pickables (berries, crops), Chests, Beehives, Map Tables, Ships.
    *   Non-permitted players CANNOT interact with: Doors, Crafting Stations, Smelters, Signs. (They also cannot auto-pickup items).
*   **Offline Raid Protection (`WardIsLove`):** Player bases within wards are protected from damage by non-permitted players *unless* at least 1 permitted player is currently online on the server.

## Server Management

*   **Server-Side Characters (`ServerCharacters`):** Player character data is stored and managed by the server, including backups.
*   **Auto-Save (`ServerCharacters`):** Server performs an auto-save every 5 minutes.
*   **Anti-Cheat (`AzuAntiCheat`):** The server checks that connecting clients have the required mods (specific list pending whitelist generation). Player stats (HP, Stamina, Carry Weight, Damage) are capped at high default values.