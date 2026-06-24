```
import discord
import random

class MyClient(discord.Client):
  async def on_ready(self):
    print('Logged on as {0}!'.format(self.user))

  async def on_message(self, message):
    if message.author == self.user:
      return

    if message.content.startswith('$hello'):
      await message.channel.send('meowie')

    if message.content.startswith('$purr'):
      await message.channel.send("ᓚᘏᗢ *purrrrrrrrr*")

    if message.content.startswith('$treat'):
      await message.channel.send("Nom nom nom!")

    if message.content.startswith('$nap'):
      await message.channel.send("The cat is sleeping. Try again later.")    

intents = discord.Intents.default()
intents.message_content = True
cat_messages = [
    "ᓚᘏᗢ meow!",
    "Don't forget to drink water!",
    "ᓚᘏᗢ *purrs approvingly*",
    "You have received +10 cat luck.",
    "The bug is hiding under the couch.",
    "ᓚᘏᗢ Good human."
]


client = MyClient(intents=intents)
client.run(the token) 

```
