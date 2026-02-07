Audio
=======================================================================================================================

*Go back to: [Cutscene Commands](Functions-CutsceneCommands.md)*

*Tip: In the GitHub web interface, click the "Outline" button to the right above the header to show the table
of contents.*

These commands allow basic playback of sounds and assorted music manipulation.


`c_soundplay`
-----------------------------------------------------------------------------------------------------------------------

> `c_soundplay(sound: sound asset)`
>
> `c_sound_play(sound: sound asset)`
>
> `c_sndplay(sound: sound asset)`
>
> `c_snd_play(sound: sound asset)`

Plays the sound `sound`. This is the same as [`c_soundplay_x`](#c_soundplay_x), with `volume` and `pitch` specified
as 0.

**Deltarune only:** The default `pitch` is 0, and `pitch` is always set as long as `volume` is not 0. This will cause
the game to attempt setting the sound's speed to 0 by default, which apparently doesn't cause unexpected behavior, but
is still a bug.

**Example:** `c_soundplay(snd_noise)` plays the sound `snd_noise`.


`c_soundplay_x`
-----------------------------------------------------------------------------------------------------------------------

> `c_soundplay_x(sound: sound asset, volume: real, pitch: real)`
>
> `c_sound_play_x(sound: sound asset, volume: real, pitch: real)`
>
> `c_sndplay_x(sound: sound asset, volume: real, pitch: real)`
>
> `c_snd_play_x(sound: sound asset, volume: real, pitch: real)`

Plays the sound `sound` at `volume` volume and in `pitch` speed.

If `volume` is 0, the sound is played at its default volume.

**Deltarune only:** `pitch` is always set as long as `volume` is not 0.

**DCSP2 only:** If `pitch` is 0, the sound is played at its default speed (which is generally 1).

**Example:** `c_soundplay_x(snd_b, 0.8, 0.9)` plays the sound `snd_b` at 0.8 volume and 0.9x speed.


`c_soundplay_wait`
-----------------------------------------------------------------------------------------------------------------------

> `c_soundplay_wait(sound: sound asset)`
>
> `c_playsound_wait(sound: sound asset)`

Plays the sound `sound`, then waits for however long the sound will ideally play for. This is equal to:

```gml
c_soundplay(sound);
c_wait_soundlength(sound);
```

**Example:** `c_soundplay_wait(snd_noise)` plays the sound `snd_noise`, and then "waits for it to finish" (i.e. waits for
its duration).


`c_mus`
-----------------------------------------------------------------------------------------------------------------------

TODO: List all `c_mus(2)` subcommands individually
