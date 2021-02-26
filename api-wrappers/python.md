# PYTHON API WRAPPERS
#### Python API Wrapper for https://infinitybots.xyz
Maintained by `Andromeda#7911`
# POST BOT STATS
## await ibl.post_stats(bot_id, auth_token, servers, shards=0)
### Example:
```py
import discord
from discord.ext import tasks

@tasks.loop(minutes=30)
async def update_ibl():
    await ibl.post_stats(bot.user.id, "auth_token", len(bot.guilds))
```
# GET USER INFO
## await ibl.user_info(id)
### Returns:
user.username <br>
- String<br><br>

user.about <br>
- String<br><br>

user.certified_dev <br>
- BOOL<br><br>

user.staff <br>
- LIST/ARRAY<br><br>

user.developer <br>
- STRING<br><br>

user.error <br>
- BOOL<br><br>

# GET BOT INFO

## await ibl.bot_info(id)

### RETURNS
bot.name<br>
bot.certified<br>
bot.tags<br>
bot.prefix<br>
bot.owner<br>
bot.library<br>
bot.short_desc<br>
bot.long_desc<br>
bot.premium<br>
bot.nsfw<br>
bot.servers<br>
bot.shards<br>
bot.votes<br>
bot.invites<br>
bot.website<br>
bot.donate<br>
bot.support<br>
bot.banner<br>
bot.staff<br>
bot.error
