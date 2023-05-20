# Dispy
An asynchronous Python Discord API library

## Upcoming
So far we only have the following:
- [x] Base Client Class
- [x] Event Handler
- [ ] All Events
- [ ] Discord Models (Messages, Users, etc.)
- [x] Commands
- [ ] Extensions/Addons
- [ ] Voice

## Basic Program
```python
import dispy

client = dispy.DiscordApp("TOKEN")
client.start()
```

## Listen to Events
```python
import dispy

client = dispy.DiscordApp("TOKEN")

@client.listen(dispy.StartedEvent) # Listen to when the bot is started
async def started_event() -> None: # This event specifically has no data, so no parameters should be present
  await client.logger.client_log("Bot started")

client.start()
```

## Prefix Command
```python
import dispy

client = dispy.DiscordApp("TOKEN")

@client.command(dispy.PrefixCommand, "foo", prefix='!')
async def foo_prefix_command(ctx:dispy.PrefixContext) -> None:
  await client.logger.client_log("bar")

client.start()
```

## Slash Command
```python
import dispy

client = dispy.DiscordApp("TOKEN")

@client.command(dispy.SlashCommand, "foo", "Messages you 'bar'")
async def foo_slash_command(ctx:dispy.SlashContext) -> None:
  await client.logger.client_log("bar")

client.start()
```
