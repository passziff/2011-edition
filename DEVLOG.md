# Development Log

## Proper Progression Update

The first update for Minecraft: The Other Update.

**Status:** Feature-complete for now. Tested in singleplayer. Not tested in multiplayer.

### Part 1: Beds, but Endgame adaptation

A Minecraft 1.0 adaptation of [Beds, but Endgame](https://github.com/passziff/beds-but-endgame).

- A Bedside Table beside the head of the bed is required to sleep
- Beds still set the player's respawn point when sleep is denied
- A Glowstone Lamp on a Bedside Table prevents nightmares
- Nightmares wake the player and block sleeping again until daytime
- F6 cycles the time of day in singleplayer Creative
- F7 can temporarily switch a singleplayer Creative session to Survival for testing and back again

#### Bedside Table

![Bedside Table](docs/images/bedside-table.png)

![Bedside Table recipe](docs/images/theotherupdate_bedsidetable_recipe.png)

#### Glowstone Lamp

![Glowstone Lamp on a Bedside Table](docs/images/glowstonelamp-on-bedsidetable.png)

![Glowstone Lamp recipe](docs/images/theotherupdate_glowstonelamp_recipe.png)

#### Current nightmare values

| Setting | Current value |
| --- | ---: |
| Nightmare chance | 40% |
| No nightmare when dawn is within | 1200 ticks |
| Time advanced by a nightmare | 600 ticks |
| Full sleep before nightmare check | 100 ticks |

A nightmare locks sleeping again until daytime. A Glowstone Lamp on the Bedside Table prevents it.

---

### Part 2: Flint & Copper

Feature-complete for now.

The current balance is intentionally documented here as a baseline for later tuning and external playtesting.

#### Flint progression

Flint forms the first tool tier before Stone.

![Flint Pebbles on different surfaces](docs/images/flint-rocks-1.png)

- Flint can be placed as small pebbles
- Flint Pebbles generate naturally on the surface and around exposed underground sediment
- Breaking a Flint Pebble returns one Flint
- Flint Pickaxes and Axes replace their wooden equivalents
- All Stone tools require smelted Stone instead of Cobblestone

##### Flint Pebbles

![Flint Pebble variants](docs/images/flint-rocks-allvariants.png)

Current generation notes:

- Shoreline Flint is limited to 25% of eligible shoreline chunks
- Underground Flint is limited to at most 2 pebbles per chunk
- Underground generation favors gravel, then dirt/sand and sediment-adjacent stone
- Isolated ordinary cave stone does not generate Flint Pebbles

##### Flint tools

![Dropped Flint tools](docs/images/flint-tools-dropped.png)

![Flint Axe equipped](docs/images/flintaxe-equipped.png)

![Flint Axe recipe](docs/images/flintaxe-recipe.png)

![Flint Pickaxe equipped](docs/images/flintpickaxe-equipped.png)

![Flint Pickaxe recipe](docs/images/flintpickaxe-recipe.png)

Flint keeps the old Wood-tier statistics:

| Stat | Flint |
| --- | ---: |
| Harvest level | 0 |
| Durability | 59 |
| Mining speed | 2.0 |
| Material damage bonus | 0 |
| Enchantability | 15 |

#### Stone progression

Cobblestone must be smelted into Stone before Stone tools can be crafted.

The current pickaxe harvest progression is:

| Tier | Harvest level | Unlocks |
| --- | ---: | --- |
| Flint | 0 | Stone / basic mining |
| Stone | 1 | Copper |
| Copper | 2 | Iron |
| Iron | 3 | Gold |
| Gold | 4 | Diamond |
| Diamond | 5 | Obsidian |

#### Copper progression

Copper forms a complete tool and armor tier between Stone and Iron.

![Copper compared with existing metal blocks and ores](docs/images/copper-comparing.png)

![Copper and Iron Ingots](docs/images/copper-iron-dropped-compared.png)

- Copper Ore drops itself and smelts into one Copper Ingot
- Nine Copper Ingots craft into a Block of Copper and can be crafted back
- Copper Ore requires a Stone Pickaxe or better
- Copper tools are stronger than Stone and weaker than Iron
- Copper armor sits between Leather and Chainmail

##### Copper tools

![Copper tools](docs/images/copper-tools.png)

Example recipe:

![Copper Pickaxe recipe](docs/images/copperpickaxe-recipe-example.png)

Current Copper tool material:

| Stat | Copper |
| --- | ---: |
| Harvest level | 2 |
| Durability | 190 |
| Mining speed | 5.0 |
| Material damage bonus | 1 |
| Enchantability | 10 |

##### Copper armor

![Dropped Copper armor](docs/images/copper-armor-dropped.png)

![Copper armor equipped](docs/images/copper-armor.png)

| Piece | Protection | Durability |
| --- | ---: | ---: |
| Helmet | 2 | 110 |
| Chestplate | 4 | 160 |
| Leggings | 2 | 150 |
| Boots | 1 | 130 |
| **Full set** | **9** | **550** |

Copper armor uses a durability multiplier of 10 and enchantability of 12.

##### Copper block hardness

| Block | Hardness |
| --- | ---: |
| Copper Ore | 2.5 |
| Iron Ore | 3.0 |
| Block of Copper | 4.0 |
| Block of Iron | 5.0 |

#### Current ore generation

![Copper Ore generation](docs/images/copperore-gen-1.png)

![Copper in a cave](docs/images/copperore-gen-2.png)

These are the current generation values after the first progression balance pass:

| Ore | Attempts / chance | Vein size | Height |
| --- | --- | ---: | --- |
| Coal | 20 attempts/chunk | 16 | Y 0-127 |
| Copper, main | 22 attempts/chunk | 7 | Y 0-55 |
| Copper, upper | 22 attempts/chunk | 6 | Y 56-127 |
| Iron, main | 9 attempts/chunk | 8 | Y 0-55 |
| Iron, rare upper | 25% chance/chunk, 1 attempt | 4 | Y 56-95 |
| Gold, main | 2 attempts/chunk | 8 | Y 0-31 |
| Gold, rare upper | 25% chance/chunk, 1 attempt | 3 | Y 32-47 |
| Redstone | 8 attempts/chunk | 7 | Y 0-15 |
| Diamond | 1 attempt/chunk | 7 | Y 0-15 |
| Lapis | Vanilla | Vanilla | Vanilla |

Rare upper Iron uses terrain-aware placement so its attempt is limited by the terrain height at the selected position.

#### Armor progression

The current protection ladder is:

| Material | Full-set protection | Durability multiplier | Enchantability |
| --- | ---: | ---: | ---: |
| Leather | 7 | 5 | 15 |
| Copper | 9 | 10 | 12 |
| Chainmail | 12 | 15 | 12 |
| Iron | 15 | 15 | 9 |
| Gold | 16 | 7 | 25 |
| Diamond | 20 | 33 | 10 |

Gold has been rebalanced into a real post-Iron armor tier while intentionally keeping its low durability and high enchantability.

#### Chainmail

Chainmail can now be obtained through normal Survival gameplay.

![Dropped Chain Links](docs/images/chainlinks-dropped.png)

Example recipe:

![Chainmail Chestplate recipe](docs/images/chainmail-chestplate-recipe-example.png)

- Any Zombie has a 20% chance to drop Chain Links
- A successful drop gives 1-3 Chain Links
- Looting currently does not modify the Chain Links drop
- Chainmail uses the normal armor recipe shapes with Chain Links
- A full Chainmail set costs 24 Chain Links
- Chainmail's existing protection and durability values are unchanged

#### Mutton and Wool

Sheep now provide food instead of an immediate source of Wool.

![Dropped Raw and Cooked Mutton](docs/images/mutton-dropped.png)

- Sheep drop 1-2 Mutton before Looting instead of Wool when killed
- Burning sheep drop Cooked Mutton
- Shearing remains the main source of Wool and gives the normal 2-4 Wool
- Nine String can be crafted into one Wool
- Raw Mutton restores 2 hunger with 0.3 saturation
- Cooked Mutton restores 6 hunger with 0.8 saturation

#### Achievements

The achievement tree now guides the changed progression and sleeping mechanics without requiring an outside guide.

![Updated achievement progression](docs/images/achievements-showcase.png)

Main progression:

`Time to Mine!` → `Hot Topic` → `Getting an Upgrade` → `Copper Age` → `Acquire Hardware` → `Gold Rush` → `DIAMONDS!`

Additional guidance:

- `Home Sweet Home` branches from `Benchmarking`
- `Bedside Manners` branches from `DIAMONDS!`
- `Sweet Dreams` branches from `We Need to Go Deeper`

---

Texture credits: copper armor item sprites based on axy's Traditional Armour. Copper ingot and block textures based on artwork by JM140628. Chain Links texture inspired by [Better Than Adventure](https://www.betterthanadventure.net/).
