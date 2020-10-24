# TalkBot

Python 3 Discord bot using Discord.py, Random Useless Facts API, and Google's Text-to-Speech via the gTTS Python library.

# Current Features

**Text-to-speech:** Using the bot's tts command (mentioning the bot with @ and using the format "tts [message to be played]") will contact Google's text-to-speech API with the desired text and save its response as tts.mp3. The bot will then join the voice channel where the user resides and FFMPEG convert/playback the mp3 over the Discord voice channel. 

**Magic 8-ball Response:**: When mentioning the bot with @ and ending the message with a question mark, the bot will reply with a randomized message and ASCII face from static.py. 

![Magic 8-ball Response](https://i.imgur.com/sqlFE6l.png "Magic 8-ball Response")

**Hi I'm Dad:** When users use I'm, I am, or similar words in server messages the bot will reply to the user with "Hi, [word after I'm], I'm Dad!". Uses regular expression matching to find the correct syntax regardless of capitalization or use/absence of apostrophe. 

![Hi I'm Dad](https://i.imgur.com/8n30Iql.png "Hi I'm Dad")

**Random Fact:** When users use the bot's random fact command (mentioning the bot with @ and putting "give me a fact" in the message), will use Python's requests library to request and display in chat a random fact via json from the [Random Useless Facts API](https://uselessfacts.jsph.pl/). 

![Random Fact](https://i.imgur.com/e7hoNmZ.png "Random Fact")

**Force disconnect from Voice Channel:** If the bot becomes stuck in a voice channel, users can mention the bot with @ and say "leave vc" to force it to disconnect. The bot will otherwise disconnect when the script is terminated. 

**End bot process:** Mentioning the bot with @ and saying "disconnect" will disconnect the bot from the Discord server and exit its process. This command is only able to be run by the bot owner as defined in secrets.py

# Usage:

Create and add your bot's account to a Discord server (detailed instructions [here](https://discordpy.readthedocs.io/en/latest/discord.html)).

Create a file named secrets.py at the root of the project folder (alongside TalkBot.py) containing the following lines:

```
OWNER_ID = "Unique ID for owner's Discord account"
CLIENT_ID = "Unique ID obtained from Discord's API Dashboard"
```

Ensure that you have [FFMPEG](https://ffmpeg.org/) installed and correctly in your environment variables. FFMPEG is used to convert the .mp3 received from gTTS for use by Discord.py.

Install Dependencies:

```
pip3 install -r requirements.txt
```

Run Bot:

```
python3 TalkBot.py
```
