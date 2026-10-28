# 🦴 Skeleton Soundboard

A dead-simple Halloween porch soundboard. Open it on a phone, point the phone at a
Bluetooth speaker, and tap an age tier when trick-or-treaters walk up — a skeleton
says something warm for the little ones, goofy for the kids, and gently roasts the
teenagers. There's also a looping dinner-party skit to run as background filler, and
a one-tap "Happy Halloween!" send-off for when a group heads back down the driveway.

No app, no accounts, no API keys, no build step. It's a single HTML page plus a folder
of pre-recorded clips. Every sound plays from a local file, so once the page loads it
makes **zero network calls**.

## Use it

Serve the folder from any static web host (or open it through a local static server)
and visit `index.html` on your phone:

- **Four age buttons** — tap the one that matches who's at the door. A random line for
  that age plays, and the button glows so you can see which one fired.
- **🎭 Full dinner-party skit** — a ~7-minute monster dinner party that **loops** as
  ambient filler. Tap to play/pause; it resumes where it left off.
- **🎃 Happy Halloween!** — a ~30-second group send-off cut from the end of the skit.
- **↻ Same again** — replay the last line.
- **■ Stop all** — stop everything and reset.

Tip for porch night: use a dedicated phone, set **Auto-Lock → Never**, turn on **Do Not
Disturb**, keep it plugged in, and pair it to a Bluetooth speaker. Then just leave the
skit looping and tap an age when kids come up.

## Layout

```
index.html         the whole app (HTML + CSS + JS, one file)
manifest.json      lists every clip and its caption, grouped by tier + the skits
audio/<tier>/*.mp3 the voice clips (under5 / 5to10 / 11to15 / teens)
skit/*.mp3         the dinner-party skit + the Happy-Halloween cut
sfx/*.mp3          sound effects used in some of the little-kid clips
lines/*.txt        the editable line pools the clips were made from (one line per row)
```

## Make it your own

The clips are just MP3s and the captions live in `manifest.json`, so you can swap in
your own voice however you like — record them, use any text-to-speech you have a license
for, whatever. The `lines/*.txt` files are the scripts the included clips came from, if
you'd rather re-voice the same material. Keep each `manifest.json` entry's `f` (file path)
and `t` (caption) in sync with the files you drop in.

## License

MIT — see [LICENSE](LICENSE). The included audio is distributed under the voice
providers' commercial-use terms; if you replace the clips, mind the license on whatever
voices you use.
