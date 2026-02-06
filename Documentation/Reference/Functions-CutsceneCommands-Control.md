Control
=======================================================================================================================

*Go back to: [Cutscene Commands](Functions-CutsceneCommands.md)*

*Tip: In the GitHub web interface, click the "Outline" button to the right above the header to show the table
of contents.*

This is a list of commands for controlling the flow of your cutscene.


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
