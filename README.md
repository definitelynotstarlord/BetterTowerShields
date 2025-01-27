# BetterTowerShields

### About
Mod to add in wackyDB files to modify both vanilla and modded tower shields into Valheim as to give them a purpose opposite bucklers and round shields.
This work was originally completed and uploaded to Thunderstore by "FactoriaTeam" via the mod [Make Tower Shields Great Again](https://thunderstore.io/c/valheim/p/FactoriaTeam/Make_Tower_Shields_Great_Again/). Unfortunately, they are not keeping their mod up-to-date nor do they add in support for any other mods -- which we will attempt to do here.

### Configuration file meanings
- ShieldStats:
  - m_blockPower = Block armor
  - m_blockPowerPerLevel = Added Block armor per upgrade
  - m_deflectionForce: Block force
  - m_deflectionForcePerLevel: Added Block force per upgrade
- m_maxDurability = Starting durability

### How blocking works
When the player is blocking:

Damage is reduced a first time by using only the blocking item's (shield or weapon) armor and resistances.
Leftover damage is reduced a second time by using the regular armor value and resistances.
Successfully blocking requires up to 10 stamina (proportional to the leftover damage value after the reduction of step one).
Blocking may fail (and the damage reduction of step one will not apply) if:
- The Stagger bar (40% of player max health) is filled after the leftover damage after reduction of step one is applied, in this case the player is also staggered.
- There is not enough Stamina available (see step three).

Additional details:

- Blocking skill increases Block armor by 0.5% for each skill point, reaching 50% at level 100.
- Block armor from the skill is not rounded (except on the tooltip).
- Blocking skill indirectly reduces the Stamina usage by increasing the Block armor.
- Blocking reduces the amount of received knockback based on the used Block armor.
- Block force is the amount of knockback dealt to the attacker when blocking melee attacks. It scales from 50% to 100% based on the used Block armor.
