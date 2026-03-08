Hi! so, basically, i created this Repository to teach you **How to make a Bot using VS Code!!**

[Table of Contents]
-------------------------------------------------------------------------------------------------------
- ### Information
   - Installation
   │
   │
   │
  - Tutorial of the Bot−−┐
   - Creating the Bot----- ┘
- ### Types of Commands
   - Normal Commands
   - Tree Commands
- ### Events
    - Creating an Event
- ### Run
    - Make the Bot Run
    - Token Tutorial
Information
-------------------------------------------------------------------------------------------------------

This Tutorial Uses **Python**, So you need to install the library first

**Link for Download**: https://www.python.org/downloads/

Installation:
-------------------------------------------------------------------------------------------------------

1.Install the VS (Visual Studio Code):

**Link for Download**: https://code.visualstudio.com/download

2. After the Download, Create a **Folder** on your **Documents**, Put any name that you want.

3. Open the **Visual Studio Code** on your Desktop and open the Folder that you've created before (if you don't know how to make this, click `Open Folder > Documents >Your Folder`)

4. Hold `Ctrl + Shift + X` and Search for **Python** From **Microsoft**

5. Then **BOOM!**, now you can use the VS Studio Code for **Python**!

-------------------------------------------------------------------------------------------------------

Creating the Bot:
-------------------------------------------------------------------------------------------------------

Before opening the VS Code, you need to first create and invite the Application on the Discord Developers.

Tutorial of the Bot:
-------------------------------------------------------------------------------------------------------

1.Open the Discord Developers
**Link:** https://discord.com/developers/applications.

2. Click on `New Application`.

3.  Go to `OAuth2` and `OAuth2 URL Generator`

and select this options:

**Scopes**:
`Bot`

**Bot Permissions**:
`Administrator`

then, invite the bot to your server

-------------------------------------------------------------------------------------------------------
After this, you need to Install the **discord.py** **Library**:

Open the Terminal:
-------------------------------------------------------------------------------------------------------

Hold `Ctrl + Shift + '` and type:

`pip install discord.py`

and now, you have the library on your VS!


Creation of the Bot:
-------------------------------------------------------------------------------------------------------
you need to first import the library to the script.

**Type**:
```
import discord
from discord.ext import commands

intents = discord.Intent.all`
bot = commands.bot("."), intents=intents) -- You can use another prefix if you want(., /, !, ?)
```
-------------------------------------------------------------------------------------------------------

Creating an Event:
-------------------------------------------------------------------------------------------------------
to the bot works, he need a Event that calls the library to activate the bot.

so, what you need to do, is create the event

**Type**:
```
@bot.event
async def on_ready():
    syncs = await bot.tree.sync() -- another type of commands
```
-------------------------------------------------------------------------------------------------------
Bot commands has **2 Types**:

Normal Commands:
-------------------------------------------------------------------------------------------------------

this type of commands is the normal ones, you just need to put your prefix and the reply command name to work.

for example:

you need a command to show another commands, a help command

So you can make it like this:

```
@bot.command()
   async def test(ctx): -- this type of command can't have space, so you need to use _
     await ctx.reply("commands: .Command1, .Command2, .Command3, ...") -- The Bot will reply your call

```  
-------------------------------------------------------------------------------------------------------

Tree Commands:
-------------------------------------------------------------------------------------------------------
This type of commands uses Interaction to work, they're more complex but is actually good to use in my opinion.

For example:

you want a command to check the bot's latency (Ping)

you can use this:

```
@bot.tree.command(name="ping", description="Check the bot's latency")
async def ping(interaction: discord.Interaction): -- You need to use this part for this type of commands work
    latency = round(bot.latency * 1000)
    await interaction.response.send_message(f"Pong! Latency: {latency} ms")
```
you can put many commands as you want, don't worry.

-------------------------------------------------------------------------------------------------------

Make the Bot to Run:
-------------------------------------------------------------------------------------------------------

after you created the commands, you need to run your bot for him to work.
so, you need to create a **SECRET TOKEN** to work
remember, this SECRET TOKEN can't be shared to anyone

-------------------------------------------------------------------------------------------------------

Token Tutorial:
-------------------------------------------------------------------------------------------------------

1. Go to the **Discord Developers**

2. Go to `Bot`

3. Then go to `Token` and click on `Reset Token`

then, you put this on the script:

```
...
bot.run("YOUR SECRET TOKEN HERE")
```
-------------------------------------------------------------------------------------------------------

and boom, you just made a functional bot using python!
