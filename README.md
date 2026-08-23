# ShowRunner

A sound cue player for theatre. One file. No install.

Drop your audio in, set your levels, hit the space bar. That's the whole job.

---

## Start it up

Double-click **`showrunner.html`**. It opens in your browser and it's ready.

Use **Chrome** or **Edge**. Works the same on Mac and on Windows.

Nothing gets uploaded. Nothing phones home. It runs offline, straight off your drive.

## Move it to another computer

Copy `showrunner.html` to a flash drive. That's it. Copy your audio folder and your
show file too, and keep all three together.

## Build your show

1. Drag your audio files onto the window. A whole folder works.
2. Every file becomes a cue, numbered in order.
3. Click a name to rename it. Click a number to change it.
4. Drag the `⋮⋮` handle to move a cue up or down.
5. Hit **Save Show**. It drops a `.show.json` in your Downloads folder.

Move that show file next to your audio folder and keep them together.

## Open a show later

Hit **Open Show** and pick your `.show.json`.

Your cues come back, but the audio doesn't — browsers aren't allowed to remember
where files live on your drive. So drag your audio folder onto the window and every
cue links back up by filename. One drag and you're live.

Rename an audio file and that cue won't find it. Keep the names alone.

## Running the show

| Key | What it does |
|---|---|
| `space` | **GO** — fire the cue you're sitting on |
| `P` | Pause everything. Hit it again to pick up where you left off |
| `↓` `↑` | Move the playhead down or up the list |
| `S` | Fade out just the selected cue |
| `F` | Fade out everything |
| `esc` | **STOP ALL.** Kills everything right now |
| `⌥↓` `⌥↑` | Move the selected cue up or down the list |
| `⌘S` / `Ctrl+S` | Save the show |
| `D` | Duplicate the selected cue |
| `Delete` | Delete the selected cue |

`esc` always wins. Even in the middle of a fade, it cuts.

Typing in a name box? The shortcuts stand down until you click away.

## What each column does

**Level** — how loud the cue plays. Set in decibels.

When you drop a file in, ShowRunner reads the whole thing, finds its loudest peak,
and sets the fader so that peak lands at −3 dB. Nothing clips. You can move any
fader after, by hand, and it takes effect on a cue that's already playing.

If a number shows up **amber**, that file is quiet at the source. The fader is
maxed at +12 dB and the cue will still sit low against the others. Turn the file
up in an audio editor.

**Re-level** puts the selected cue back to its automatic level. With nothing
selected it does the whole list.

**In** — seconds to fade up when the cue starts. `0` means it comes in at full level.

**Out** — seconds to fade out when *you stop the cue*. It does **not** fade the
end of the file. A door slam plays all the way through and stays a door slam.

**Follow** — what happens to the next cue down the list:

- **Hold** — nothing. It waits for you to hit GO.
- **Continue** — the next cue fires right along with this one. Use it to stack a
  music bed under an effect, or to fire three cues off one GO.
- **Follow end** — the next cue fires when this one finishes playing.

**Wait** — seconds to hold before the follow fires. Works with both kinds.

Chain them and one GO can run a whole sequence. The playhead jumps past the whole
chain, so your next GO is the next cue *you* have to fire.

**Loop** — plays over and over until you stop it. A looping cue never ends, so
**Follow end** won't fire off it.

## Cues stack

Firing a cue does not stop the one before it. Music keeps running under your
effects, the way it should.

- The `▶` on a row plays that cue right now.
- The `■` on a row fades it out.
- Playing cues show up along the bottom. Each one has its own stop button.

## Output

**Output** picks which device the sound goes to. Leave it on **System default** and
it follows your Mac or PC sound setting.

Browsers hide device names until you allow audio access once. Hit **Names** if you
want to see the real names in the list. The list works either way.

## Audio it reads

MP3, WAV, AIFF, M4A, AAC, OGG, FLAC, OPUS.

Whole files load into memory before the show, so a GO fires instantly — no
spinning up a file off the drive mid-scene.

## Before you go into tech

- Copy the folder to the show computer and open it there.
- Load your show and check every cue is linked. Missing files turn **red**.
- Play every cue once, at show volume, through the real speakers.
- Test your longest follow chain end to end.
- Find `esc` with your eyes closed.
- The amber dot by the show name means you have unsaved changes.

## Things worth knowing

**Pause freezes time.** Follow cues wait too. A follow that was 5 seconds out is
still 5 seconds out when you resume.

**Don't reload the page mid-show.** You'll lose the audio links and have to drag
the folder back in. It warns you first.

**No database, no settings file.** Everything is either in your show file or in
this one HTML file. Nothing hides.

---

Built for Ethan Entermedia.
