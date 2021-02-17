import discord
from discord.ext import commands
import os


HEY = "I have woken  up from a 4 line sleep"

client = discord.Client()

Client = commands.Bot(command_prefix = '-')


@client.event
async def on_ready():
  print('Succesfully turned on ')
  
@client.event
async def on_message(message):
  if message.author == client.user:
    return
  
  if message.content.startswith("Fix"):
    await message.channel.send("SHITNA WIFI")

  if message.content.startswith('!SPAM'):
    await message.channel.send('SPAM X2')

  if message.content.startswith('Hey'):
    await message.channel.send('Whats up')
  
  if message.content.startswith('!Python'):
    await message.channel.send('I learned python from https://www.youtube.com/watch?v=kqtD5dpn9C8&t=2846s&ab_channel=ProgrammingwithMosh')
  
  if message.content.startswith("!Site"):
    await message.channel.send("http://127.0.0.1:5500/Html.html")



  if  message.content.startswith('!FavPlaylist'):
    await message.channel.send('My favorite playlist is The ultimate anime bash by Jake-Live')
  

  if  message.content.startswith('Code'):
    await message.channel.send('https://github.com/OtakuTheProgrammingSide/Otaku.py/blob/main/Source%20code%20+%20disclaimer%20till%20line%205.md')
  

  if message.content.startswith('!cmd'):
    await message.channel.send('1: Hey 2: !Python 3: FavPlaylist 4: code 5: !SPAM 6: !cmd 7: .join // number 7 in development')

  


  return


client.run(os.getenv('TOKEN'))

@client.command(pass_context=True)
async def join(ctx):
  await ctx.author.voice.channel.connect()
