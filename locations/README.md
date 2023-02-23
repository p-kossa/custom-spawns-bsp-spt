# Nooky's Custom Spawns for BetterSpawnsPlus
![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square)

# Changes
## All maps
- more PMC spawns within the first ~20 mins, more SCAVs later in raid
- more bot spawns in POIs (i.e. Customs Dorms, Shoreline Resort, etc.)
- more PMC spawns near actual PMC spawn points from live

## Customs
- high chance of PMC groups at Dorms early in raid
- more bot spawns at Dorms early in raid

## Shoreline
- more PMC activity at Resort early in raid
- more bots in general at and near Resort early-mid raid
- more late SCAVs near edges of map

## Labs
- add Raider group spawns early in raid
- PMC group spawns early in raid

## Reserve
- more PMC activity at Barracks early in raid

## Woods
- more SCAVs scattered near extracts toward end of raid
  - SCAVs will be spawn later on at "UN ROADBLOCK"; more PMCs early instead

## How Does This Work?

`BossEscortAmount`
This key is specifically for bot groups. We can use `BossChance` to define the % chance that the given bot has "followers".

Let's use an example:
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
- in the Dorms zone `ZoneDormitory`


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
- in the Crossraods zone `ZoneCrossRoad`

## Map Zones

