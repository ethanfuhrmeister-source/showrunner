# ShowRunner

A sound cue player for theatre. One file. No install.

Drop your audio in, set your levels, hit the space bar. That's the whole job.

---

## Start it up

Double-click **`showrunner.html`**. It opens in your browser and it's ready.

Use **Chrome** or **Edge**. Works the same on Mac and on Windows.

Nothing gets uploaded. Nothing phones home. It runs offline, straight off your drive.

## Move it to another computer

Keep everything in one folder:

```
Twelfth Night/
  showrunner.html
  Twelfth Night.show.json
  Audio/
    01 Preshow.mp3
    02 Door Slam.mp3
```

Copy that whole folder to a flash drive, then on the other machine open
`showrunner.html` and **drag the folder onto the window**. You get the cue list and
all its audio in one drop. Nothing else to click.

A stray audio file sitting in the folder won't sneak into your show. When a show file
is in the drop, ShowRunner only relinks what the show already asks for.

## Build your show

1. Drag your audio files onto the window. A whole folder works.
2. Every file becomes a cue, numbered in order.
3. Click a name to rename it. Click a number to change it.
4. Drag the `⋮⋮` handle to move a cue up or down.
5. Hit **Save Show** and put the file in your show folder, next to your audio.

The first save asks where to put it. Every save after that goes straight back to the
same file — no dialog, no Downloads folder. `⌘S` while you build just works.

To save a copy somewhere else, shift-click **Save Show** or press `⌘⇧S`.

On a browser without file-saving support you'll get a normal download instead. If that
happens, move the file out of Downloads and into your show folder yourself.

## Open a show later

Quickest way: drag the show folder onto the window. Show file and audio, one drop.

Or hit **Open Show** and pick the `.show.json`. Then drag your audio folder in, because
browsers aren't allowed to remember where files live on your drive. Every cue links
back up by filename.

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
| `⌘S` / `Ctrl+S` | Save the show, in place |
| `⌘⇧S` / `Ctrl+Shift+S` | Save a copy somewhere new |
| `A` | Audition the selected cue from the marker |
| `W` | Show or hide the waveform |
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

**Re-level** puts the selected cue back to its automatic level. Shift-click it to do
every cue in the show at once.

**In** — seconds to fade up when the cue starts. `0` means it comes in at full level.
You can drag this on the waveform instead of typing it.

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

**Loop** — plays over and over until you stop it. It loops your trimmed section, not
the whole file, so you can loop a clean bar of music. A looping cue never ends, so
**Follow end** won't fire off it.

## The waveform

The panel at the bottom shows the selected cue. Click any cue and it follows along.
`W` hides it when you want the full cue list back.

**Trim the top and tail.** Grab the green bar on the left or the red bar on the right
and drag. The dimmed parts are the bits you cut — they never play. The cue's length
in the list updates as you drag, and trimmed cues get a ✂ next to the time.

**Set the fades by hand.** The amber tabs along the top strip are your fade handles.
Drag the left one right to fade in. Drag the right one left to fade out. The amber
curve is the real shape of the fade you'll hear, not a straight line — that's why it
looks bent.

The top strip belongs to the fades. Everything below it belongs to the trim bars. So a
fade sitting at zero is still grabbable even though it's parked on top of a trim bar.

**Find your cut.** Click anywhere on the waveform to drop a dashed marker, then hit
**Audition** or press `A` to play from there. Audition ignores the trim and fires no
follow cues — it's just you listening.

**Watch it run.** The blue playhead tracks the cue while it plays.

**Start** and **End** up top take typed numbers if you want to be exact. **Reset trim**
puts the whole file back.

Trimming never touches your audio file. It's just numbers in the show file.

## Fade cues and Stop cues

Not every cue plays audio. Two kinds act on a cue that's already running, so a fade
becomes a numbered cue you fire in sequence instead of something you have to remember
to do by hand.

**Fade cue** — ramps its target to a level over a time.

- Pick the target where an audio cue shows its filename.
- The fader sets the level it fades **to**. Drag it all the way down and it reads
  **OUT** — that fades to silence and stops the target.
- The **Out** column is the fade time.
- Fade *up* too. Set it to −6 dB and a bed that was sitting at −20 comes up under a
  scene, still running.

**Stop cue** — cuts its target dead. No fade, no fade time.

Both can target **Everything** instead of one cue, so an end-of-show "stop all" can be
a real cue at the bottom of your list.

Add them with **Fade cue** and **Stop cue** in the toolbar. Whatever cue you have
selected becomes the target, so select the music, then click Fade.

They obey Follow and Wait like any other cue. A Fade cue's "end" is the end of its
ramp, so **Follow end** on a 10 second fade fires the next cue 10 seconds later.

Firing one at a cue that isn't playing does nothing and tells you so.

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

- Copy the whole show folder to the show computer and open it there.
- Drag the folder onto the window. Check every cue is linked — missing files turn **red**.
- Play every cue once, at show volume, through the real speakers.
- Check your trims. A cue that plays 8 seconds in the list should play 8 seconds.
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
