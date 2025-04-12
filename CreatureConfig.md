# Creature Level and Loot Control - Custom Configuration (`CreatureConfig.yml`)

This document explains the various configuration options available in `CreatureConfig.yml` for customizing creature behavior, levels, loot, and more using the Creature Level and Loot Control (CLLC) mod for Valheim.

## 1. Defining Custom Creature Groups (`groups`)

You can create custom groups to apply settings to multiple creature types at once. Define them under the top-level `groups` key.

```yaml
groups:
  My Plains Group:  # A custom name for your group
    - Deathsquito
    - Fuling Berserker
    - Lox
  Strong Enemies:
    - Troll
    - Fuling Berserker
    - Lox
  My Bosses:
    - The Elder
    - Moder
```

*   **Usage:** Define a group name (e.g., `My Plains Group`) followed by a colon and a list of creature prefab names.
*   **Built-in Groups:** The mod implicitly includes groups for each biome (e.g., `Meadows`, `Black Forest`), plus special groups: `all` (all creatures), `creature` (all non-boss creatures), `boss` (all bosses).

## 2. Biome and Group Specific Overrides

Most configuration settings can be applied specifically to biomes or custom groups by using the biome/group name as a top-level key.

```yaml
# Example: Apply settings only to the Meadows biome
Meadows:
  # ... settings specific to Meadows ...

# Example: Apply settings only to the custom group "My Plains Group"
My Plains Group:
  # ... settings specific to creatures in this group ...
```

*   **Priority:** Settings are evaluated in a specific order (detailed later), but generally, more specific settings (like for a single creature) override broader settings (like for a biome or `all`).

## 3. Star Level Chances (`stars`)

Controls the probability (%) for creatures in a specific group/biome to spawn with 1 or more stars, based on the current world level.

```yaml
Meadows:
  stars:
    # World Level 0: 10% chance for 1-star, 2% chance for 2-star
    0: [10, 2]
    # World Level 1: 15% chance for 1-star, 5% for 2-star, 1% for 3-star
    1: [15, 5, 1]
    # ... up to world level 5
    5: [30, 15, 8, 3, 1]

Mountain:
  stars:
    # Use the default settings from the main CLLC config file for world level 0
    0: default
    # Custom settings for world level 1
    1: [15, 3, 2]
```

*   **Format:** `world_level: [chance_1_star, chance_2_star, chance_3_star, ...]`
*   **Calculation:** The chance for a 0-star creature is `100% - sum_of_chances`. For `0: [10, 2]`, the 0-star chance is `100 - (10 + 2) = 88%`.
*   **`default`:** Uses the corresponding setting from the main mod configuration file (usually `BepInEx/config/fluix.mods.creaturelevelcontrol.cfg`).

## 4. Creature Effects (`effect`)

Controls the probability (%) for creatures to spawn with special effects (like `Armored`, `Regenerating`, `Quick`, etc.). Can be disabled or configured per world level.

```yaml
Meadows:
  effect:
    # Disable the Armored effect completely in Meadows at world level 0
    Armored: 0
```

*   **Format:** `EffectName: probability` or `EffectName: 0` to disable.
*   **World Levels:** You can nest effect configurations under world levels like the `stars` setting if needed, although the example only shows disabling at world level 0.
*   **Note:** Zero-star creatures cannot normally have effects. Effect probability settings typically apply starting from 1-star creatures.

## 5. Creature Infusions (`infusion`)

Controls the probability (%) for creatures to spawn with elemental infusions (`Lightning`, `Fire`, `Frost`, `Poison`, `Chaos`, `Spirit`). Can be configured per world level and per star level.

```yaml
Meadows:
  infusion:
    # At world level 0, disable Chaos infusion
    0:
      Chaos: 0
    # At world level 1, disable Chaos infusion
    1:
      Chaos: 0
    # From world level 2 onwards, use default Chaos infusion settings
    2:
      Chaos: default

Swamp:
  infusion:
    # World Level 0: Poison infusion chance depends on creature stars
    # 0-star: 5%, 1-star: 10%, 2-star: 15%, 3-star: 20%, 4+-star: 25%
    0:
      Poison: [5, 10, 15, 20, 25]
    # World Level 1: Increased chances
    1:
      Poison: [10, 15, 20, 25, 30]
    # ... up to world level 5
    5:
      Poison: [30, 35, 40, 45, 50]
```

*   **Format (World Level):** `world_level: { InfusionName: probability }`
*   **Format (World Level & Star):** `world_level: { InfusionName: [prob_0_star, prob_1_star, ...] }`
*   **`default`:** Uses the corresponding setting from the main mod configuration file.
*   **Multiple Infusions:** You can define chances for multiple infusions within the same world level. The total probability for all infusions should not exceed 100%.
