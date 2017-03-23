# twitch-cli

Simple twitch tool for command-line that does only two things.

```
$ twitch
┌──────────────┬───────────────────────────────────────────┬─────────────────────┬─────────┐
│ name         │ status                                    │ game                │ viewers │
├──────────────┼───────────────────────────────────────────┼─────────────────────┼─────────┤
│ followgrubby │ Grubby - HL - w/ Commentary, Q&A Welcome! │ Heroes of the Storm │ 4141    │
├──────────────┼───────────────────────────────────────────┼─────────────────────┼─────────┤
│ tehreaver    │ CHAMP IS BACK. LETS GO CHAMP              │ Overwatch           │ 110     │
└──────────────┴───────────────────────────────────────────┴─────────────────────┴─────────┘
$ twitch followgrubby
[cli][info] Found matching plugin twitch for URL twitch.tv/followgrubby
[cli][info] Available streams: audio, mobile (worst), low, medium, high, source (best)
[cli][info] Opening stream: source (hls)
[cli][info] Starting player: mpv --cache 2048
```

## features

- Display your followed channels currently online
- Open a channel in a media player with [`streamlink`][streamlink]

## requirements

- nodejs
- [`ramda-cli`][ramda-cli]
  - Install: `npm install -g ramda-cli`
- [`streamlink`][streamlink]
  - Install: `pip install streamlink`

## usage

`$ twitch [channel] [quality]`

## setup

An OAuth token is required to get your followed channels from Twitch API.

1. Register a new application at https://www.twitch.tv/kraken/oauth2/clients/new
    - Application name can be whatever
    - Enter `https://twitchapps.com/tokengen/` as Redirect URI
2. Get OAuth token from https://twitchapps.com/tokengen/
    - Enter the Client ID acquired from first step
    - Enter `user_read` as scope
4. Download `twitch` executable to somewhere in your `$PATH`
    - `curl https://raw.githubusercontent.com/raine/twitch-cli/master/twitch > ~/bin/twitch`
    - `chmod +x ~/bin/twitch`
3. Edit `twitch` executable and set `OAUTH_TOKEN` and `CLIENT_ID` to the obtained values

[streamlink]: https://streamlink.github.io
[ramda-cli]: https://github.com/raine/ramda-cli
