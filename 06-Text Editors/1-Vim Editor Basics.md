# Vim Editor Basics

Vim is a highly configurable and powerful text editor that is an enhanced version of the older Vi editor. It is commonly used in Unix-like operating systems, and mastering Vim can significantly boost your productivity when editing text or code.

## Understanding Vim's Modes

Vim operates in several modes, each designed for different tasks:

- **Normal Mode**: This is the default mode for navigating and manipulating text. Most of Vim's powerful commands are executed in this mode.
- **Insert Mode**: In this mode, you can insert or modify text. Enter this mode by pressing `i`, `I`, `a`, `A`, `o`, or `O`.
- **Visual Mode**: Used for selecting text. You can enter visual mode by pressing `v` for character-wise selection or `V` for line-wise selection.
- **Command-Line Mode**: Accessed by pressing `:` in Normal Mode, this mode allows you to execute more complex commands like saving, quitting, and searching.

### Switching Between Modes

- **Normal Mode**: Press `Esc` to switch to Normal Mode from any other mode.
- **Insert Mode**: Press `i` to enter Insert Mode.
- **Visual Mode**: Press `v` to enter Visual Mode.
- **Command-Line Mode**: Press `:` to enter Command-Line Mode.

## Basic Vim Commands

### Opening Vim

To start editing a file with Vim:

```bash
vim filename
```

If the file does not exist, Vim will create it upon saving.

### Navigating in Normal Mode

- **h, j, k, l**: Move the cursor left, down, up, and right, respectively.
- **w**: Move the cursor to the beginning of the next word.
- **b**: Move the cursor to the beginning of the previous word.
- **0**: Move the cursor to the beginning of the line.
- **$**: Move the cursor to the end of the line.
- **gg**: Move to the beginning of the file.
- **G**: Move to the end of the file.
- **Ctrl+f**: Scroll down one screen.
- **Ctrl+b**: Scroll up one screen.

### Inserting Text

- **i**: Insert before the cursor.
- **I**: Insert at the beginning of the line.
- **a**: Insert after the cursor.
- **A**: Insert at the end of the line.
- **o**: Open a new line below the current line and enter Insert Mode.
- **O**: Open a new line above the current line and enter Insert Mode.
### Editing Text

- **x**: Delete the character under the cursor.
- **dw**: Delete from the cursor to the start of the next word.
- **dd**: Delete the entire line.
- **u**: Undo the last change.
- **Ctrl+r**: Redo the undone change.
- **p**: Paste text after the cursor.
- **y**: Yank (copy) text.
- **yy**: Yank the current line.
- **P**: Paste text before the cursor.

### Saving and Quitting

- **:w**: Save the file (write changes).
- **:q**: Quit Vim (close the file).
- **:wq**: Save and quit.
- **:q!**: Quit without saving changes.
- **:x**: Save and quit (same as `:wq`).

### Searching and Replacing

- **/pattern**: Search forward for "pattern".
- **?pattern**: Search backward for "pattern".
- **n**: Move to the next occurrence of the search pattern.
- **N**: Move to the previous occurrence of the search pattern.
- **:%s/old/new/g**: Replace all occurrences of "old" with "new" in the entire file.
- **:s/old/new/g**: Replace all occurrences of "old" with "new" in the current line.
