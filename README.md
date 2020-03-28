# DiscordPostQ3ServerStatus
Very simple project to post to a Discord webhook if a Quake3 server has players connected.

# sendDiscordMessage
This script is escaping the input and properly formats it in JSON format and then posts to a defined Discord Webhook.
Credits go to https://github.com/mturley/curl-discord-cronjob

# serverstatus
This script runs in a loop and every 2 minutes checks the status of a Quake3 server (or any QStat supported gameserver) and assuming it's not empty it will post an update to the Discord webhook. 
Once a server is considered active (meaning there are players on it) and the message to Discord has been posted the script will not post any other updates to the Discord webhook for this gameserver until it has gone inactive and then active again. This is to avoid spamming.

# Dependencies:
- python (for JSON escaping)
- QStat (https://github.com/multiplay/qstat)
- Discord server with Webhook enabled (https://support.discordapp.com/hc/en-us/articles/228383668-Intro-to-Webhooks)

There are definitely more elegant ways to do this but this works for me :-)
