Control
=======================================================================================================================

*Go back to: [Cutscene Commands](Functions-CutsceneCommands.md)*

*Tip: In the GitHub web interface, click the "Outline" button to the right above the header to show the table
of contents.*

These commands allow controlling the flow of your cutscene.

TODO: Move some of these to main page, and then some of the text/sound-specific stuff to their own pages,
basically this page is probably going to be teared down


`c_instant`
-----------------------------------------------------------------------------------------------------------------------


`c_wait`
-----------------------------------------------------------------------------------------------------------------------

> `c_wait(amount: real)`

Waits for `amount` frames before proceeding to the next command.

Wait commands like `c_wait` only block the execution of cutscene commands; for example, it doesn't prevent everything
else in the host instance's Step event from running every frame.

**Example:** `c_wait(30)` generally waits for 1 second (Deltarune and Undertale target 30FPS).


`c_wait_if`
-----------------------------------------------------------------------------------------------------------------------

> `c_wait_if(objectid: instance, a_name: string, operator: string, b: any)`

Waits until instance `objectid`'s variable named `a_name` satisfies the comparison to `b` per operator `operator`.
`objectid` must always exist during the wait.

`operator` can be one of the following comparison operators (wrapped with quotes as it is a string).
These operators work just like [their GML equivalents][gml-ops]:

- `"="`: Checks whether `a` is equal to `b`. Note the **single** equal sign.
- `"!="`: Checks whether `a` is not equal to `b`.
- `">="`: Checks whether `a` is greater than or equal to `b`.
- `"<="`: Checks whether `a` is less than or equal to `b`.
- `">"`: Checks whether `a` is greater than to `b`.
- `"<"`: Checks whether `a` is less than to `b`.

[gml-ops]: https://manual.gamemaker.io/lts/en/GameMaker_Language/GML_Overview/Expressions_And_Operators.htm#operators

**Example:** `c_wait_if(mc_actor, "image_index", "<=", 0)` waits until the `image_index` of `mc_actor`
is less than or equal to `0` (i.e. the `mc` actor instance is on the first frame of its sprite).


`c_wait_talk`
-----------------------------------------------------------------------------------------------------------------------

> `c_wait_talk()`
>
> `c_waittalk()`


`c_wait_box`
-----------------------------------------------------------------------------------------------------------------------

> `c_wait_box(msgno: real)`


`c_wait_box_end`
-----------------------------------------------------------------------------------------------------------------------

> `c_wait_box_end(msgno: real)`


`c_wait_soundlength`
-----------------------------------------------------------------------------------------------------------------------

> `c_wait_soundlength(sound: sound asset)`

Waits for however long the sound `sound` would ideally play for.

**Example:** `c_wait_soundlength(snd_noise)` "waits for" `snd_noise` "to finish" (i.e. waits for its duration).


`c_waitcustom`
-----------------------------------------------------------------------------------------------------------------------

`c_waitcustom_end`
-----------------------------------------------------------------------------------------------------------------------


`c_customfunc`
-----------------------------------------------------------------------------------------------------------------------

`c_delay_customfunc`
-----------------------------------------------------------------------------------------------------------------------


`c_saveload`
-----------------------------------------------------------------------------------------------------------------------

`c_terminatekillactors`
-----------------------------------------------------------------------------------------------------------------------
