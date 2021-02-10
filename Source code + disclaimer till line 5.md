# Otaku.py
My discord bot code

This bot wont work until u create a .env file and inside paste in your token after "Token=" no spaces 

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

  if message.content.startswith('!SPAM'):
    await message.channel.send('SPAM X2')

  if message.content.startswith('Hey'):
    await message.channel.send('Whats up')
  
  if message.content.startswith('!Python'):
    await message.channel.send('I learned python from https://www.youtube.com/watch?v=kqtD5dpn9C8&t=2846s&ab_channel=ProgrammingwithMosh')



  if  message.content.startswith('!FavPlaylist'):
    await message.channel.send('My favorite playlist is The ultimate anime bash by Jake-Live')
  
  if message.content.startswith('!Play tuab'):
    await message.channel.send("Playing TheUltimateAnimePlaylist by Jake-Live")
  
  print('Something was typed')

  return

client.run(os.getenv('TOKEN'))

@client.command(pass_context=True)
async def join(ctx):
  await ctx.author.voice.channel.connect()
