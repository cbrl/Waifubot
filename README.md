# Waifubot
A simple Discord.js bot that grabs a random picture from gelbooru upon typing "waifu" or a related command. Defaults to SFW images only; server moderator can change the setting.

## Requirements
### Libraries
- fs
- request-promise-native
- entities
- xml2js
- mathjs
- forever


## Setup
Requires a file to be created in the config folder:
#### oauth2.json
```
{
  "token": "YOUR_TOKEN_HERE"
}
```

Where YOUR_TOKEN_HERE is the OAuth2 token for your Discord bot account.

## Commands
All picture grabbing commands respond with a post with an embedded image and the text:
> "[Username], your [waifu/husbando/etc] is [character name]"

The bot registers a command regardless of the position or case of the word in a post, so even `asdfWaIfUqwerty` will work.

If a post starts with "waifu" or "husbando", any following words will be treated as tags for the search.

The base tags for every search are `[1girl/1boy, solo, -original]`

The aliases.json file contains a list of shortened tags that can be used for these commands.

### Image Searching
- **waifu** - Gets a random post with a single girl

- **husbando** -  Same as waifu, only searches for dudes

- **touhou** - Gets a random (female) Touhou character

- **tankgirl** - Gets a random character from the series _Girls Und Panzer_

- **shipgirl** - Gets a random image from Kantai Collection

- **monstergirl** - Gets a random image from Monster Musume no Iru Nichijou

### Settings & Help
- **@Waifubot help** - Displays a help message with all of the commands

- **@Waifubot nsfw on|off** - Enables or disables the inclusion of nsfw pictures in the search

- **@Waifubot aliases text** - Sends a DM with a list of aliases for tags

- **@Waifubot aliases file** - Sends a DM with the aliases file. Easier to read and search through.
