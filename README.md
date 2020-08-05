# TTT-Custom-Roles

Adds a bunch of new roles to the Garry's Mod TTT gamemode, as seen on the Yogscast and Achievement Hunter's let's play.

**Steam workshop page:** https://steamcommunity.com/sharedfiles/filedetails/?id=2125529065

### Special Thanks:

- [Jenssons](https://steamcommunity.com/profiles/76561198044525091) for the 'Town of Terror' mod which was the inspiration for this mod.
- Thanks to Noxx, Lix3, and Kommandos0 for the original version of this mod.
- Thanks to Malivil for fixing the voice chat in their version
- Thanks to [SPAYED]Bud for the emt role

### Compatibility issues

Some weapon mods cause the team shops to bug out and only display one item (The one that is causing the issue). Here are some mods with known compatibility issues:

- [TTT Gravity Changer](https://steamcommunity.com/sharedfiles/filedetails/?id=1618719637)
- [Time Manipulator](https://steamcommunity.com/sharedfiles/filedetails/?id=1318271171)
- [TTT Blue Firework](https://steamcommunity.com/sharedfiles/filedetails/?id=1421303070)
- [TTT Scarface Jihad Bomb](https://steamcommunity.com/sharedfiles/filedetails/?id=917717470)

# Gameplay instructions

## Innocent Team:
Goal: Kill all members of the traitor team

**Innocent**
- A standard player. Has no special abilities

**Detective**
- All other players are notified of the Detectives at the start of the round
- Can search bodies of dead players
     - Reveals the role, what killed them, who they last saw and other useful information to all players
     - If other players try to search a body it will instead alert Detectives of the body’s location (Optional)
- Has access to a shop
     - Spawns with two credits
     - Gains a credit whenever a member of the traitor team is killed

**Glitch**
- Has a chance to spawn instead of an Innocent
- Appears as a Traitor (or Zombie) to members of the traitor team
- Prevents members of the traitor team from using team text and voice chat

**Mercenary**
- Has a chance to spawn instead of an Innocent
- Has access to a shop
     - Spawns with one credit
     - Can buy any naturally occuring weapon or items available to both Detectives and Traitors

**Phantom**
- Has a chance to spawn instead of an Innocent
- Haunts attackers on death
     - Haunted players leave a smoke trail behind them
     - Killing the haunted player will revive the Phantom on 50 health
     - Detectives are notified when the Phantom is killed or revived

## Traitor Team:
Goal: Kill all members of the innocent team

**Traitor**
- Notified of team members and Jesters at the start of the round
- Has access to a shop
     - Spawns with one credit
     - Gains a credit whenever enough innocent team members are killed

**Assassin**
- Has a chance to spawn instead of a Traitor
- Notified of team members and Jesters at the start of the round
- Given a random target at the start of the round
     - Deals double damage to the target and half damage to all other players
     - When the target dies a new target is selected
     - Detectives will always be the final targets
     - Killing the wrong player will fail the contract and the Assassin will deal half damage to all players
- Has access to a basic shop
     - Spawns with no credits
     - Gains a credit whenever enough innocent team members are killed

**Hypnotist**
- Has a chance to spawn instead of a Traitor
- Notified of team members and Jesters at the start of the round
- Spawns with a brain washing device
     - When used on a dead body it will revive them at full health
     - Changes the role of the revived player to Traitor
     - Cannot be used on Jesters and Swappers
- Has access to a basic shop
     - Spawns with no credits
     - Gains a credit whenever enough innocent team members are killed

**Vampire**
- Has a chance to spawn instead of a Traitor
- Notified of team members and Jesters at the start of the round
- Spawns with fangs
     - When used on a dead body it will destroy the body and heal 50 health up to a maximum of 125 health
     - Right click will grant short term speed and invisibility on a cooldown
- Has access to a basic shop
     - Spawns with no credits
     - Gains a credit whenever enough innocent team members are killed

**Zombie**
- Has a chance to spawn instead of all Traitors
- Notified of team members and Jesters at the start of the round
- Spawns with claws
     - Deals 50 damage to members of the innocent team
     - If used to kill a player they will repsawn as a zombie
- Deals half damage will all standard weapons
- Has access to a perk shop
     - Spawns with no credits
     - Gains a credit upon infecting another player with the claws

## Independent Players:

**Jester (Goal: Get killed by another player)**
- Has a chance to spawn instead of an Innocent
- Deals no damage to other players or props
- Takes no environmental damage (e.g. fire, fall, explosion...)
- Can message members of the traitor team using team text and voice chat but will not recieve replies

**Swapper (Goal: Get killed by another player and then fulfill their old goal)**

- Has a chance to spawn instead of an Innocent
- Appears as a Jester to members of the traitor team
- Deals no damage to other players or props
- Takes no environmental damage (e.g. fire, fall, explosion...)
- Can message members of the traitor team using team text and voice chat but will not recieve replies
- When killed by another player the Swapper swaps roles with their attacker
     ◦ The attacker will die instead and the Swapper will respawn with the newly swapped role
     ◦ If a Detective searches the body of the attacker they will look like a Swapper

**Killer (Goal: Be the last player standing)**

- Has a chance to spawn instead of an Innocent
- Spawns with 150 health and maximum health
- Traitors are notified if there is a Killer
- Has access to a shop
     - Spawns with one credit
     - Can buy any naturally occuring weapon or items available to both Detectives and Traitors

# Server config options

Add the following to your server config:

```cpp
// ----------------------------------------
// Custom Role Settings
// ----------------------------------------

ttt_glitch_enabled    1 // (Default: 1): Whether the Glitch should spawn or not
ttt_mercenary_enabled 1 // (Default: 1): Whether the Mercenary should spawn or not
ttt_phantom_enabled   1 // (Default: 1): Whether the Phantom should spawn or not
ttt_assassin_enabled  1 // (Default: 1): Whether the Assassin should spawn or not
ttt_hypnotist_enabled 1 // (Default: 1): Whether the Hypnotist should spawn or not
ttt_vampire_enabled   1 // (Default: 1): Whether the Vampire should spawn or not
ttt_zombie_enabled    1 // (Default: 1): Whether Zombies should spawn or not
ttt_jester_enabled    1 // (Default: 1): Whether the Jester should spawn or not
ttt_swapper_enabled   1 // (Default: 1): Whether the Swapper should spawn or not
ttt_killer_enabled    1 // (Default: 1): Whether the killer should spawn or not
ttt_emt_enabled       1 // (Default: 0): Whether the EMT should spawn or not

// Role Spawn Chances
ttt_glitch_chance    0.25 // (Default: 0.25): Chance of the Glitch spawning in a round
ttt_mercenary_chance 0.25 // (Default: 0.25): Chance of the Mercenary spawning in a round
ttt_phantom_chance   0.25 // (Default: 0.25): Chance of the Phantom spawning in a round
ttt_assassin_chance  0.20 // (Default: 0.20): Chance of the Assassin spawning in a round
ttt_hypnotist_chance 0.20 // (Default: 0.20): Chance of the Hypnotist spawning in a round
ttt_vampire_chance   0.20 // (Default: 0.20): Chance of the Vampire spawning in a round
ttt_zombie_chance    0.10 // (Default: 0.10): Chance of Zombies replacing traitors in a round
ttt_jester_chance    0.25 // (Default: 0.25): Chance of the Jester spawning in a round
ttt_swapper_chance   0.25 // (Default: 0.25): Chance of the Swapper spawning in a round
ttt_killer_chance    0.25 // (Default: 0.25): Chance of the Killer spawning in a round
ttt_emt_chance       0.25 // (Default: 0.25): Chance of the EMT spawning in a round

// Role Spawn Requirements
ttt_glitch_required_innos       2 // (Default: 2): Number of innocents for the Glitch to spawn
ttt_mercenary_required_innos    2 // (Default: 2): Number of innocents for the Mercenary to spawn
ttt_phantom_required_innos      2 // (Default: 2): Number of innocents for the Phantom to spawn
ttt_assassin_required_traitors  2 // (Default: 2): Number of traitors for the Assassin to spawn
ttt_hypnotist_required_traitors 2 // (Default: 2): Number of traitors for the Hypnotist to spawn
ttt_vampire_required_traitors   2 // (Default: 2): Number of traitors for the Vampire to spawn
ttt_jester_required_innos       2 // (Default: 2): Number of innocents for the Jester to spawn
ttt_swapper_required_innos      2 // (Default: 2): Number of innocents for the Swapper to spawn
ttt_killer_required_innos       3 // (Default: 3): Number of innocents for the Killerto spawn
ttt_emt_required_innos          2 // (Default: 2): Number of innocents for the EMT to spawn

// Karma
ttt_karma_jesterkill_penalty 50   // (Default: 50): Karma penalty for killing the Jester
ttt_karma_jester_ratio       0.5  // (Default: 0.5): Ratio of damage to Jesters, to be taken from karma

// Weapon Shop
ttt_shop_merc_mode      0 // How to handle Mercenary shop weapons. All modes include weapons specifically mapped to the Mercenary role. 0 (Disable) - Do not allow additional weapons. 1 (Union) - Allow weapons available to EITHER the Traitor or the Detective. 2 (Intersect) - Allow weapons available to BOTH the Traitor and the Detective. 3 (Detective) - Allow weapons available to the Detective. 4 (Traitor) - Allow weapons available to the Traitor.
ttt_shop_assassin_sync  0 // Whether Assassins should have all weapons that vanilla Traitors have in their weapon shop
ttt_shop_hypnotist_sync 0 // Whether Hypnotists should have all weapons that vanilla Traitors have in their weapon shop
ttt_shop_vampire_sync   0 // Whether Vampires should have all weapons that vanilla Traitors have in their weapon shop

//EMT Variables
ttt_emt_hot_initial		20 // The immediate health boost from the EMT Healing Ray
ttt_emt_hot_amount		5  // The amount of health received per interval from the Healing Ray HoT
ttt_emt_hot_charges		3  // The ammo for the EMT Healing Ray

// Other
ttt_zombie_pct              0.25 // (Default: 0.25): Percentage of total players that will be a Zombie
ttt_mer_credits_starting    1    // (Default: 1): Number of credits the Mercenary starts with
ttt_kil_credits_starting    2    // (Default: 2): Number of credits the Killer starts with
ttt_assin_credits_starting  0	 // (Default: 0): Number of credits the Assassin starts with
ttt_hypno_credits_starting  0	 // (Default: 0): Number of credits the Hypnotist starts with
ttt_vamp_credits_starting   0	 // (Default: 0): Number of credits the Vampire starts with
ttt_detective_search_only   1   // (Default: 1): Whether only detectives can search bodies or not
```