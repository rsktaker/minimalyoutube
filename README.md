# minitube

A YouTube player that shows the video and nothing else. No feed, no search, no recommendations, no comments.

**Live:** https://minitube-ivory.vercel.app

Paste a YouTube link and it plays. When the video ends, you are back at the empty page.

## Use

- Paste a link into the page, or paste over a playing video to switch.
- Put a link after the address: `minitube-ivory.vercel.app/https://youtu.be/VIDEO_ID`
- Or use `?v=VIDEO_ID&t=90` to start at 90 seconds.

Watch, `youtu.be`, shorts, embed and live links all work. It remembers where you stopped in each video.

| Key | Action |
| --- | --- |
| Space, `k`, click | Play or pause |
| ← → | Back or forward 5 seconds |
| `j` `l` | Back or forward 10 seconds |
| ↑ ↓ | Volume |
| `m` | Mute |
| `f`, double click | Fullscreen |
| `<` `>` | Speed |
| `0`–`9` | Jump to 0%–90% |
| Esc | New link |

## How it works

It is one HTML file with no build step. The video is YouTube's own embedded player with its controls turned off. A transparent layer takes every click, and the player is drawn three times taller than its window, so YouTube's title bar and "more videos" shelf fall outside what is shown.

Videos whose owners disabled embedding will not play.

## Run it yourself

Serve the folder over http and send every path to `index.html`. YouTube refuses to play on `file://` pages.

```
npx serve -s .
```

`vercel.json` does the same on Vercel.

## License

MIT
