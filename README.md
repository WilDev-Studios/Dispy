# Dispy
An asynchronous Python Discord API library

## Upcoming
So far we only have the following:
- [x] Base Client Class
- [x] Event Handler
- [ ] All Events
- [ ] Discord Models (Messages, Users, etc.)
- [ ] Commands
- [ ] Extensions/Addons
- [ ] Voice

## Basic Program
```python
import dispy

client = dispy.DiscordApp("TOKEN") # Initialize a Discord application

@client.listen(dispy.StartedEvent) # Listen to when the bot is started
async def started_event() -> None:
  await client.logger.client_log("Bot started")
 
client.start() # Start running the Discord application
```
