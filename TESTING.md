# Testing guide

Thanks for helping test Clutch! This guide walks through everything Clutch can do, one scenario
at a time. You don't have to do all of it: pick the parts that match how you'd really use it
(streaming, recording, clipping games, video calls…), and come back for more later.

**How to use this guide**

- Each scenario has **steps** and what **you should see**. If something doesn't match, that's a
  bug worth reporting, even if it seems small.
- Anything confusing, slow or annoying counts too: report it as a **Suggestion**.
- Use the [Bug report](../../issues/new?template=bug.yml) or
  [Suggestion](../../issues/new?template=suggestion.yml) form. One issue per problem.
- Tick a scenario off in your head (or in a note) as you go, and say in the issue which scenario
  number you were on, e.g. "4.2".

**Logs.** For crashes and anything technical, attach the newest file from Clutch's logs folder:

- Windows: press Win+R, paste `%APPDATA%\Clutch\logs` and press Enter.
- Linux: `~/.config/Clutch/logs`.

**Tips**

- Almost everything can be undone with **Ctrl+Z** (redo: Ctrl+Shift+Z).
- **Ctrl+K** opens the command palette, which can run any action by name.
- Before streaming publicly, you can test going live to an unlisted YouTube stream or a
  test channel.

---

## 1. Install and first start

**1.1 Install (Windows)**
1. Run `Clutch-<version>-x64.msi`. If SmartScreen warns, click *More info → Run anyway*.
2. On the **Shortcuts** page, leave "Add Clutch to the Start menu" checked; tick the desktop one
   if you want it.
3. Finish with "Launch Clutch" checked.

You should see: Clutch opens. Clutch shows up when you type "Clutch" in Windows search, and on
the desktop if you ticked it.

**1.2 Install (Linux)**
1. `chmod +x Clutch-*.AppImage`, then run it.

You should see: Clutch opens. If something is missing (PipeWire, a portal, a keyring), Clutch
should tell you in plain words instead of failing silently.

**1.3 First-run setup**
1. Pick a purpose: streaming games, talking to camera, recording videos, or vertical video.
2. Read the list of what Clutch found (screen, webcam, mic, encoder).
3. Try once with **Choose the resolution myself** too (you can make a new setup later, see 2.6).

You should see: a ready scene matching your choice, your screen or game in the preview, your
webcam placed sensibly, and your mic in the sound controls with noise suppression on.

**1.4 Upgrade**
When a new beta comes out, install it over the old one.

You should see: your scenes, settings and stream keys are all still there.

---

## 2. Building scenes

**2.1 Scenes**
1. Add a scene (**+** next to Scenes, or Ctrl+Shift+N), rename it (F2), duplicate it, delete it.
2. Click between scenes.

You should see: the preview switches instantly; undo brings back a deleted scene.

**2.2 Add each kind of source** (Add source, or Ctrl+N), one at a time:
- **Display capture**: your whole screen. Try the cursor toggle and, with two monitors, the
  monitor picker.
- **Window capture**: one app's window. Close and reopen that app: Clutch should pick it up again
  by itself.
- **Game capture** (Windows): a game, ideally in borderless fullscreen.
- **Video capture device**: webcam or capture card. Try a different resolution or frame rate.
- **Image**: PNG, JPEG, WebP or an animated GIF.
- **Color** and **Text**: try font, outline, shadow, gradient.
- **Media**: a video or audio file. Try a playlist (several files or a folder), loop, shuffle,
  and images mixed in for a slideshow. Use play/pause, previous/next and the position bar.
- **Browser**: a web page, for example an alert or chat widget URL. Click **Refresh**.
- **Application audio**: the sound of a single app (e.g. Spotify or Discord).

You should see: each source appears in the preview (or in the sound controls for audio-only
ones) without stutter, and its settings apply right away.

**2.3 Arrange things on the canvas**
1. Drag a source to move it; drag its corners to resize; rotate it.
2. Alt+drag an edge to crop.
3. Move it near edges and other sources: it should snap, with guide lines.
4. Nudge with the arrow keys.
5. Try the quick buttons: Full screen, Center, the four corners, Fit (Ctrl+F), Stretch,
   Reset (Ctrl+R).
6. Reorder (Ctrl+] / Ctrl+[), group (Ctrl+G), hide/show and delete (Del) sources.

**2.4 Video filters**
Add filters to a source (color correction, LUT, chroma key / green screen, luma key, crop/pad,
blur, sharpen, image mask, custom shader), reorder and remove them.

You should see: the effect live in the preview; removing the filter restores the original.

**2.5 Multiple canvases** (e.g. horizontal and vertical at once)
1. Use the canvas tabs above the preview to add a vertical canvas (1080×1920).
2. Build a scene on it using the same webcam as the horizontal canvas.
3. Rename and remove a canvas, then undo.

You should see: the same webcam works on both canvases at once without "device busy" errors.

**2.6 Setups** (the pill in the top bar)
1. **New setup…** (runs the first-run setup again; try cancelling it too), **Rename…**,
   **Duplicate**, **Delete…**.
2. Switch between setups.
3. Try switching while recording.

You should see: switching swaps all scenes and sounds; while recording or live, switching is
blocked with a clear message.

---

## 3. Sound

**3.1 Sound knobs** (each audio source has a round knob)
1. **Drag up/down** or **scroll** on a knob: the volume changes and the dB value shows.
2. **Single click**: nothing should happen.
3. **Double-click**: mutes (crossed-out speaker, dimmed). Double-click again to unmute.
4. **Ctrl+click**: volume back to 0 dB.
5. Talk or play something: the knob should glow with the level.

**3.2 Sound settings**
1. Click a source's **name** under its knob to open its settings. Close with the **×** or Esc.
2. Try **Hear on my speakers**, balance, sync offset and the track buttons.

**3.3 Voice effects**
1. On your mic's settings, turn on "Hear on my speakers" (use headphones!).
2. Try each **Voice** preset: Deeper, Higher, Robot, Radio, Cave, Echo, then Off.
3. Fine-tune the voice filters it added.

You should see: the effect within a moment, with no crackling or noticeable delay.

**3.4 Audio filters**
Add and remove noise suppression, noise gate, compressor, gain and limiter on your mic.

**3.5 No double sound**
1. Have a game or window capture with **Capture audio** on, plus Desktop audio.
2. Play a media source with "Hear on my speakers" on.
3. Record 30 seconds and listen back.

You should see (and hear): every sound exactly once in the recording, no echo or doubling.

---

## 4. Recording

**4.1 Basic recording**
1. Click **Record**, wait a minute, stop.
2. Open the recording (Clips view → Show → **Recordings**).

You should see: smooth video, in-sync audio, the correct length.

**4.2 Long recording**
Record for 30+ minutes while gaming or browsing.

You should see: no growing delay between audio and video, no stutter, and no audio-dropout
alerts.

**4.3 Recording several canvases**
With two canvases (2.5), set recording to record every canvas.

You should see: one file per canvas, named after it.

**4.4 Recordings in the Clips view**
Play, rename, favorite, show in folder, copy, trim (**Save as new clip** and **Replace**) and
delete a recording.

---

## 5. Clips

**5.1 Replay buffer by hand**
1. Start the replay buffer from the controls panel.
2. After something happens, click **Save clip** (or Ctrl+Shift+R).

You should see: a new clip in the Clips view with the last seconds.

**5.2 Clip mode and the clip hotkey**
1. Settings → Clips: turn on **Clip mode**, keep the hotkey **F8** (or set your own), turn on
   **Sound when saved**.
2. Start a game. If Clutch asks "Is … a game?", answer.
3. Play, and press the hotkey a few times.

You should see: a sound each time, and clips tagged with the game's name in the Clips view, even
though you weren't recording or streaming. The hotkey should work while the game has focus.

**5.3 Auto-clip** (Counter-Strike 2, Dota 2 or League of Legends)
1. Settings → Clips → Auto-clip: **Connect** your game (restart CS2/Dota 2 afterwards).
2. Under **Rules for**, choose the events you want and the seconds before/after.
3. Play a match.

You should see: clips of your kills/wins/objectives saved by themselves; events close together
merged into one clip (up to **Longest clip**). Spectating someone else must not create clips.

**5.4 Managing clips**
Play, rename, favorite, trim, copy, show in folder and delete clips; filter by game.

**5.5 Storage limit**
Set a low storage limit (e.g. 1 GB) and keep clipping.

You should see: the oldest automatic clips get deleted; favorites and your own clips stay.

---

## 6. Montages

**6.1 Auto-montage**
1. Open **Montages**, pick some clips and/or a recording's highlights.
2. Add music (optional), choose a length (e.g. 60 s), format (16:9, 9:16, 1:1) and order.
3. Build it, preview it, then export.

You should see: cuts that land on the music's beats, and an exported video that plays everywhere
(phone, Discord, YouTube).

**6.2 Editing a montage**
Trim segments, reorder them, relink a missing file, and export again.

---

## 7. Going live

**7.1 Go live on one platform**
1. Click **Go Live**, pick Twitch, YouTube, Kick or Facebook Live.
2. Use **Where do I find it?** to get your stream key and paste it.
3. Go live for a few minutes, then stop.

You should see: the stream on the platform in good quality; no "dropped frames" or network
alerts on a good connection.

**7.2 Several platforms at once**
1. In the menu next to Go Live, **Add platform**.
2. Go live on both.
3. While live, stop and restart just one of them.

You should see: the other platform keeps streaming without a hiccup.

**7.3 Advanced**
In **More options**, try a custom server, or your own encoder and bitrate.

**7.4 Bad network**
While live, briefly disconnect Wi-Fi/Ethernet (~10 s), then reconnect.

You should see: a clear warning, then Clutch reconnects on its own.

**7.5 Stream keys are remembered**
Close and reopen Clutch.

You should see: you don't have to paste your key again.

---

## 8. While you're live

**8.1 Live deck**
While live, use the Live deck: switch scenes (F1–F9), adjust sound with the knobs, open a
source's sound settings from its name, and go **Back to the live controls**.

**8.2 Studio mode and transitions**
1. Turn on studio mode: you get a Preview next to the Program.
2. Change the Preview's scene, then send it with **Transition**, **Cut** or **Fade**.
3. Try every transition type: Fade, Fade to color, Slide, Swipe, Wipe, **Stinger** (a video
   file), and Custom shader. Change direction, color and duration.

You should see: smooth transitions; sound from both scenes blends during the switch.

**8.3 Chat**
1. Open **Chat**, sign in inside each platform's tab.
2. Send a message.

You should see: one tab per platform you stream to; you chat as yourself.

**8.4 Viewer count**
Connect your Twitch/YouTube account (Settings → Stream). While live, click the viewer count in
the top bar.

You should see: total viewers, and a per-platform breakdown.

---

## 9. Automation

**9.1 Macro with a hotkey**
1. Click the lightning button in the top bar.
2. Create a macro: e.g. "switch to BRB scene" + "mute mic", triggered by a hotkey.
3. Press the hotkey while a game is in front.

You should see: the macro runs, and Ctrl+Z in Clutch undoes what it did.

**9.2 Other triggers**
Try: a window coming to the front (e.g. your game's name), every N seconds, a scene going live,
recording/stream starting or stopping. Add a **Wait** step and a **Save clip** step.

---

## 10. Virtual camera

1. Click the camera button in the top bar (Windows may ask for permission once).
2. In Discord, Zoom, Teams or Google Meet, pick **Clutch Virtual Camera** as your camera.
3. Choose which canvas it shows in Settings → Virtual camera.

You should see: your Clutch scene as your webcam in the call, smooth and not mirrored wrongly.

Linux: needs `v4l2loopback` first (`sudo modprobe v4l2loopback card_label="Clutch" exclusive_caps=1`).

---

## 11. Stats and health

1. While recording or live, click the stats in the status bar at the bottom of the window.
2. Push your PC: run a heavy game, or set a very high bitrate.

You should see: live numbers and 5-minute graphs, and plain-language alerts (rendering lag,
encoder overload, network trouble, high CPU/GPU, low disk, audio dropouts) with advice that
makes sense. Alerts should go away once things calm down.

---

## 12. Remote control (Stream Deck, Touch Portal, Streamer.bot)

1. Settings → **Remote control**: turn it on, note the address and password.
2. Connect your Stream Deck / Touch Portal / Streamer.bot using its obs-websocket v5 plugin.
3. Switch scenes, start/stop recording, and run a macro from it.

---

## 13. Everyday use

These are the bugs that matter most, so please keep an eye out all the time:

- **Crashes or freezes**, especially when plugging in/unplugging a webcam, mic, headset or
  monitor while Clutch is open.
- **Sleep / lock**: put your PC to sleep with Clutch open, wake it up, keep using Clutch.
- **Light and dark mode**: switch your system theme; everything should stay readable.
- **Small windows and scaling**: shrink the window, try 125%/150% display scaling.
- **Keyboard only**: Tab through the app; can you reach everything?
- **Performance**: does your game run noticeably worse with Clutch open? Tell us your FPS with
  and without Clutch.
- **Words**: any text that's unclear, wrong or misspelled.

---

## Linux: what's different

- Screen and window capture use your desktop's picker; Clutch remembers your choice
  (**Choose again…** in the source settings).
- **Game capture isn't available**; use window or display capture.
- Global hotkeys go through your desktop's shortcut settings (KDE, GNOME 48+) and your desktop
  may ask once. Elsewhere they only work while Clutch is in front.
- The "window comes to the front" trigger works only on X11.
- Stream keys are kept in your keyring (GNOME Keyring, KWallet). Without one, a key lasts until
  Clutch closes.

When reporting a Linux bug, please include your distro, desktop (GNOME/KDE/…), and whether
you're on Wayland or X11.
