# Nooky's Custom Spawns for BetterSpawnsPlus
![Version: 1.2.1](https://img.shields.io/badge/Version-1.2.1-informational?style=flat-square)

# Usage

PreyToLive's BetterSpawnsPlus is *REQUIRED* - so please go download and install that first!  
https://hub.sp-tarkov.com/files/file/1002-betterspawnsplus/

Once installed, all custom spawn files go in this directory (from the mod folder):
`db/locations/<MAP_NAME>/botSpawn.json`

Just copy and paste and that's it!

# Spawn Changes
All of my spawn configurations are designed with 60 min. raid timers max (other than Factory and Labs which are 45 min. each). Compared to default BSP, my spawns are more PMC heavy, especially in the first half of the raid. **You will see more bot activity earlier in your raids** - especially PMCs.

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


## Can I create my own?

Yes! That's bascically what I've done here - thanks to PreyToLive, the spawn configurations are fairly straightforward and easy to understand. Creating spawns is simply adding an additional json object into your `botSpawn.json` files. Feel free to experiment!
