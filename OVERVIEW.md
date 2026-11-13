# Computer Use

Lets Claude, Codex and Oh My Pi agents see and operate desktop applications on
the Paseo daemon host. This fork supports macOS and Linux with Niri.

On Niri, agents list apps and windows, focus an intended window, read a screenshot,
then click, drag, scroll, type, paste or press shortcuts. Every input is followed
by fresh state. Captures cover the whole target display, including other visible
windows, and coordinates account for fractional scaling.

Requires Paseo 0.13 or later, Node 22, an unlocked Niri session, grim, wayvnc and
wl-clipboard. Enable Computer Use in settings and create a new agent to receive
the tools. Input uses a private local Unix socket, without exposing a VNC network
port. Existing Host screen installations can remain enabled independently.

One agent controls the desktop at a time. Paseo Stop, disabling Computer Use,
ending a turn or closing its connection cancels control. Input requires the
intended window to stay focused. Password managers and configured app ids are
blocked, including in visible workspaces being captured. Browser apps are off by
default and have a separate setting.

Niri changes real focus and pointer position. It has no accessibility tree,
element indexes, background input, global Escape/shake stop, virtual overlay or
same-window human activity pause. Unicode paste preserves previous plain text
where possible; non-text clipboard data is refused. Windows and other Linux
compositors are not supported in this version.

The original macOS backend requires macOS 14 or later, Xcode Command Line Tools,
Accessibility and Screen Recording permissions, and retains its indexed controls
and background-input features.

Screenshots and application text returned by tools reach the agent and its model
provider. The plugin does not silently save screenshots to disk.
