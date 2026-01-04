# Bot Commands Quick Guide

Player accounts can run the bot commands below (security level is `SEC_PLAYER`). Use them in chat with a leading dot, e.g. `.bot info`.

## General bots (`.bot`)
- `.bot start` / `.bot stop` — enable or unload the bot system.
- `.bot reload` — reload bot config and database entries.
- `.bot info` — show current bot stats.
- `.bot add <name>` — log in an existing character as a bot.
- `.bot add_all` — load every registered bot.
- `.bot ranadd [count]` — add random bots from the `playerbot` table.
- `.bot delete <name>` — disconnect a bot by character name.

## Party companion bots (`.partybot`)
Spawns a combat companion near you; useful for questing/dungeons.

- `.partybot add <role|class>` — create a new bot nearby. Roles: `tank`, `healer`, `dps` (random), `meleedps`, `rangedps`. Classes: `warrior`, `paladin` (Alliance), `hunter`, `rogue`, `priest`, `shaman` (Horde), `mage`, `warlock`, `druid`.
- `.partybot clone` — clone your selected player as a bot at your position.
- `.partybot load <name>` — load an existing character as a bot at your position.
- `.partybot setrole <tank|dps|meleedps|rangedps|healer>` — change the selected party bot’s role.
- `.partybot attackstart` / `.partybot attackstop` — make party bots attack/stop attacking your selected target.
- `.partybot pull` — order bots to pull your selected target.
- `.partybot aoe` — order bots to AoE your selected target.
- `.partybot ccmark <1-8>` / `.partybot focusmark <1-8>` / `.partybot clearmarks` — control crowd-control and focus marks.
- `.partybot cometome` — summon party bots to you.
- `.partybot usegobject` — interact with your selected game object.
- `.partybot pause` / `.partybot unpause` — pause or resume party bot AI.
- `.partybot unequip` — make the selected party bot unequip gear.
- `.partybot remove` — remove the selected party bot.

Notes: Bots cannot be added while you are dead, in combat, in instances (unless checks are skipped), or flying; cloning requires the target to be alive and same faction.

## Battleground bots (`.battlebot`)
Fills BG queues with temporary bots.

- `.battlebot add alterac|arathi|warsong <team> <level> [temporary]` — enqueue a battleground bot (team: `alliance` or `horde`; temporary `0|1`).
- `.battlebot remove <name>` — remove a specific battle bot.
- `.battlebot removeall` — remove all battle bots.
- `.battlebot showpath` / `.battlebot showallpaths` — debug movement paths.

Server option: `BattleBot.AutoJoin` will auto-queue bots to meet minimum team sizes.

## Saving and config
- Bot saving is governed by `PlayerBot.AllowSaving` (default off). Enable in `mangosd.conf` if you want bots to save progress.
- Random bots require entries in the `playerbot` table; party bots can be created on the fly.
