# ImpossibleDragon (Paper 1.21.11)

A brutal, multi-phase Ender Dragon fight. Needs Java 21.

## Build
```
mvn clean package
```
Jar ends up in `target/ImpossibleDragon-1.0.0.jar` -> drop into `plugins/`.

## Features
- 800 HP dragon (configurable), damage reduction + per-hit damage cap
- 3 phases (100-66%, 66-33%, <33% ENRAGED with faster cooldowns)
- Explosive dragon fireballs, wither skull barrages
- Telegraphed lightning strikes
- Endermen / vex / phantom minion waves (no loot)
- Tail strike (telegraphed sweep with knockback)
- Lightning breath (charge at the mouth, dodgeable beam)
- Animated purple magic circles + spinning shield around every crystal
- Roar (darkness/nausea/slow) and levitation-drop attack
- Pillar crystals respawn; alive crystals heal the dragon extra
- Dragon lifesteal + damage multiplier
- Bonus XP and item rewards on death

## Commands (`impossibledragon.admin`, alias `/idragon`)
- `/idragon status` - HP, phase, crystals, minions
- `/idragon reload` - reload config and re-apply stats
- `/idragon retune` - re-apply max-health to active dragons

Everything is tweakable in `config.yml`.

## Bedrock (Geyser)
Bedrock players get action-bar warnings + a sound before tail strikes, lightning breath and ground lightning, since Java particles may not render for them. See `effects.warning-text` (`bedrock` | `everyone` | `off`).

## Shield + crystal timers
- The dragon is immune while shielded. Destroyed crystals each get their own respawn timer
  (floating text + a ring that fills up on the ground).
- Destroy ALL crystals before they come back -> shield breaks, dragon lands and is vulnerable.
- Window over / phase gate reached -> shield reforms and every crystal returns.
- 10 minute clock in the boss bar; after that the dragon goes DOOM.

## Rebirth (final form)
The first time the dragon would die, it refuses: it becomes invulnerable for a few seconds while
its health refills to 50%, every crystal returns and the shield comes back. It then fights in
PHASE 4 (FINAL FORM) with faster attacks and +25% damage. The second death is real.
