# Volume!

Alfred workflow for quickly setting or adjusting the macOS output volume.

This version updates the original workflow for compatibility with **macOS Tahoe 26.2**.

## Requirements

* Alfred 5

## Installation

1. Download or clone this workflow.
2. Open Alfred.
3. Go to **Workflows**.
4. Import the `.alfredworkflow` file by double-clicking it, or drag it into Alfred's Workflows window.

## Usage

Open Alfred and type:

```text
vol <value>
```

### Set volume

Set the volume to an absolute percentage:

```text
vol 50
```

Sets the output volume to **50%**.

### Increase volume

Prefix the value with `+`:

```text
vol +10
```

Increases the current volume by **10%**.

The volume is capped at 100%.

### Check volume

Use `?`:

```text
vol ?
```

Displays the current volume and mute status.

## macOS Tahoe compatibility

The workflow uses `/usr/bin/osascript` to communicate with macOS's volume controls.

The volume calculations are performed in Bash before calling AppleScript. This avoids relying on AppleScript to evaluate Alfred's input directly and makes the workflow more robust on newer macOS versions.

## Changes from the original workflow

* Explicitly uses `/usr/bin/osascript`.
* Calculates relative volume changes in Bash.
* Validates absolute volume values before applying them.
* Prevents volume from exceeding 100%.
* Simplifies the volume-status query.
* Updated for macOS Tahoe 26.2.

## Credits

Based on the original **Volume!** workflow by [BaksiLi](https://github.com/BaksiLi/AlfredWorkflows).
