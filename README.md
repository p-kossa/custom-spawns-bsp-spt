# Nooky's Custom Spawns for BetterSpawnsPlus
![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square)

# Usage

PreyToLive's BetterSpawnsPlus is *REQUIRED* - so please go download and install that first!  
https://hub.sp-tarkov.com/files/file/1002-betterspawnsplus/

Once installed, all custom spawn files go in this directory (from the mod folder):
`db/locations/<MAP_NAME>/botSpawn.json`

Just copy and paste and that's it!

**Note:** `spawnChangesOnlyPreset.json` is OPTIONAL - it's my personal config file for BSP, it uses all defaults except for slightly longer raid times tuned for my custom spawns.

# Spawn Changes
## All maps
- minor increase to all bot spawns
- more PMC spawns within the first ~20 mins, more SCAVs later in raid
- more bot spawns in POIs (i.e. Customs Dorms, Shoreline Resort, etc.)
- more PMC spawns near actual PMC spawn points from live

## How Does This Work?

`BossEscortAmount`
This key is specifically for bot groups. We can use `BossChance` to define the % chance that the given bot has "followers".

Let's look at an example for **Customs**:
```json
{
  "BossName": "sptUsec",
  "BossChance": 80,
  "BossZone": "ZoneDormitory",
  "BossPlayer": true,
  "BossDifficult": "normal",
  "BossEscortType": "sptUsec",
  "BossEscortDifficult": "normal",
  "BossEscortAmount": "2",
  "Time": 120,
  "Supports": null,
  "TriggerId": "",
  "TriggerName": "",
  "Delay": 0,
  "RandomTimeSpawn": false
}
```
Spawn a USEC PMC with:
- an 80% chance of having "followers"
- 100% of having 2 "followers" (so, PMC trio in this case)
- at 120 seconds into the raid
- in the zone `ZoneDormitory`


Let's look at a different example:
```json
{
    "BossName": "assault",
    "BossChance": 80,
    "BossZone": "ZoneCrossRoad",
    "BossPlayer": false,
    "BossDifficult": "normal",
    "BossEscortType": "assault",
    "BossEscortDifficult": "normal",
    "BossEscortAmount": "0,0,0,0,1",
    "Time": 70,
    "Supports": null,
    "TriggerId": "",
    "TriggerName": "",
    "Delay": 0,
    "RandomTimeSpawn": false
}
```
Spawn a SCAV with:
- an 80% chance of having "followers"
- an 80% chance of having 0 "followers", a 20% chance of having 1 "follower"
- at 70 seconds into the raid
- in zone `ZoneCrossRoad`

With the above YOU TOO can write your own custom spawns to experiment with.
