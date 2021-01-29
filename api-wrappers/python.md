# Python Library

## Python Wrapper

This is our official python library used for interacting with the Infinity Bots API.

> Maintainer: `Andromeda.txt#7911`

### Installation

#### Windows 10:

Assuming you have python 3.7+ and pip installed:

```text
pip install ibl
```

#### REPL.IT

[REPL.IT](https://repl.it/) is a great website to test code. To use it, put the two following lines at the top of your script:

```text
import os
os.system('pip install ibl')
```

#### Linux \(Ubuntu + Debian\)

Assuming you have Python 3.7+ and pip3 installed:

```text
sudo pip3 install ibl
```

### Ratelimits

You can POST Server and Shard Count stats once every 5 minutes

**Rate Limit Structure**

| ROUTE | REQUEST | REQUESTS ALLOWED PER 5 MINUTES |
| :--- | :--- | :--- |
| /api/bots/:botid | POST | 1 |

### Post Method

v1 RESTful API

#### POST/api/bots/:botid

Requires authentication

**Responses**

| STATUS | CODE | DESCRIPTION |
| :--- | :--- | :--- |
| Success | 200 | Your stats have been posted |
| Not Found | 404 | Couldn’t find bot |
| Rate Limit | 429 | You’re being ratelimited one request per 5 mins |
| Internal Server Error | 500 | An error occurred, Contact Dexter |
| Error | 400 | Something went wrong here. |

**Constructor**

```text
ibl(client, token)
```

**POST Example**

```text
import ibl
import discord
from discord.ext import commands

bot = commands.Bot(command_prefix="! ")


@bot.event
async def on_ready():
    print('Bot online')

@bot.command()
@commands.is_owner()
async def poststats(ctx):
    await ibl.post_stats(bot.user.id, "infinity_auth_token", len(bot.guilds), 
number_of_shards)
    await ctx.send('Bot stats posted')

bot.run("discord_bot_token")
```

### Get method

v1 RESTful API

#### GET/api/bots/:botid/info

**Response**

| STATUS | CODE | DESCRIPTION |
| :--- | :--- | :--- |
| Success | 200 | GET Request Successful |
| Not Found | 404 | Couldn’t find bot |

**Constructor**

```text
IBL()
```

**GET Example \(BOT INFO\)**

```text
import ibl
import discord
from discord.ext import commands

bot = commands.Bot(command_prefix="! ")

@bot.event
async def on_ready():
    print('Bot online')

@bot.command()
async def botinfo(ctx,id):
    bots_info = await ibl.bot_info(id)
    embed=discord.Embed(title=f"Info on {bots_info.bot_name}", description = 
    f'''
    Name:{bots_info.bot_name}
    Certified:{bots_info.certified}
    Tags:{bots_info.tags}
    Prefix:{bots_info.prefix}
    Owner:{bots_info.owner}
    Library:{bots_info.library}
    Description:{bots_info.short_desc}
    Servers:{bots_info.servers}
    Shards:{bots_info.shards}
    Votes:{bots_info.votes}
    Website:{bots_info.website}
    Donate:{bots_info.donate}
    Support:{bots_info.support}
    Staff:{bots_info.staff}
    '''
    )
    await ctx.send(embed=embed)

bot.run("discord_bot_token")
```

