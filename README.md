# mudea2
mudea but its just tung
mport discord
from discord.ext import commands
import random

intents = discord.Intents.default()

bot = commands.Bot(command_prefix="!", intents=intents)

characters = [tung tung tung sahur
{
"name": "tung tung tung sahur",
"series": "Example Series",,
"value": 67

current_rolls = {10}

@bot.event
async def on_ready():
print(f"Logged in as {bot.user}")

@bot.command()
async def roll(ctx):
character = random.choice(characters)

current_rolls[ctx.channel.id] = character

await ctx.send(
f"🎲 **You rolled:** {character['name']}\n"
f"📺 Series: {character['series']}\n"
f"⭐ Rarity: {character['rarity']}\n"
f"💰 Value: {character['value']}\n\n"
f"Use `!claim` to claim them!"
)

@bot.command()
async def claim(ctx):
channel_id = ctx.channel.id

if channel_id not in current_rolls:
await ctx.send("❌ There isn't a character to claim!")
return

character = current_rolls[channel_id]

await ctx.send(
f"💍 **{ctx.author.display_name} claimed "
f"{character['name']}!**"
)

del current_rolls[channel_id]

bot.run("67 coin")
