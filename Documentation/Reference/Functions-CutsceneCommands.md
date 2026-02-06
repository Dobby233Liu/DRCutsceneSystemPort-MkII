Cutscene Commands
=======================================================================================================================


Sub-Pages
-----------------------------------------------------------------------------------------------------------------------

*Tip: In the GitHub web interface, click the "Outline" button to the right above the header to show the table
of contents.*

- Commands by category
  - [Control](Functions-CutsceneCommands-Control.md)
  - [Actor](Functions-CutsceneCommands-Actor.md)
  - [Instance](Functions-CutsceneCommands-Instance.md)
  - [Dialogue](Functions-CutsceneCommands-Dialogue.md)
  - [Audio](Functions-CutsceneCommands-Audio.md)
  - [Camera](Functions-CutsceneCommands-Camera.md)

- [Miscellaneous Information](#miscellaneous-information)


`c_cmd`
-----------------------------------------------------------------------------------------------------------------------

> `c_cmd(command: string, arg1: any, arg2: any, arg3: any, arg4: any)`

Pushes the command `command` to the command queue, with `arg1, arg2, arg3, arg4` as the parameters to it.

Other `c_*` functions are generally wrappers of either this or [`c_cmd_x`](#c_cmd_x).
The content of `command` in `c_cmd` calls, however, is not always 1:1 to what is seen in `c_*` function names.

**Example:** `c_cmd("wait", 30, 0, 0, 0)` equals to [`c_wait(30)`](Functions-CutsceneCommands-Control.md#c_wait).


`c_cmd_x`
-----------------------------------------------------------------------------------------------------------------------

> `c_cmd_x(command: string, arg1: any, arg2: any, arg3: any, arg4: any, arg5: any, arg6: any)`

Pushes the command `command` to the command queue, with `arg1, arg2, arg3, arg4, arg5, arg6` as the parameters to it.
This supports 2 more arguments than [`c_cmd`](#c_cmd).

Other `c_*` functions are generally wrappers of either this or `c_cmd`.
The content of `command` in `c_cmd_x` calls, however, is not always 1:1 to what is seen in `c_*` function names.

**Example:** `c_cmd_x("wait", 30, 0, 0, 0, 0, 0)` equals to [`c_wait(30)`][c_wait].

[c_wait]: Functions-CutsceneCommands-Control.md#c_wait


`c_delaycmd`
-----------------------------------------------------------------------------------------------------------------------


`c_delaycmd4`
-----------------------------------------------------------------------------------------------------------------------


`c_arg_objectxy`
-----------------------------------------------------------------------------------------------------------------------


`c_globalvar`
-----------------------------------------------------------------------------------------------------------------------


`c_debugprint`
-----------------------------------------------------------------------------------------------------------------------


Miscellaneous Information
-----------------------------------------------------------------------------------------------------------------------

- <a id="avoid-keywords-for-inst"></a>For commands with instances as parameters, you should not pass `self` or `other`;
  these keywords will likely not refer to what you intend them to refer to. \
  Use instance IDs instead, such as `id` instead of `self`, or `other.id` instead of `other`.
