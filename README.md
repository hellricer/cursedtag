<p align="center">
  <h3 align="center">cursedtag</h3>

  <p align="center">
        A console audio tag editor.
  </p>

  <p align="center">
        <a href="https://asciinema.org/a/EE1zL5opMz7HcVaL1kYs7EyNY" target="_blank"><img src="https://asciinema.org/a/EE1zL5opMz7HcVaL1kYs7EyNY.svg" width="70%"/></a>
  </p>
<br>

- Works in terminal / console.
- Tiny (written in *bash*, using few external utilities).
- Supports mp3, ogg & flac files.
- Inspired by [EasyTAG's](https://github.com/GNOME/easytag) features
  and [cursetag's](https://github.com/lotuskip/cursetag) look (and name).
- Can operate on multiple files:
  - apply field to all selected files,
  - bulk rename files based on tags,
  - fill tags from file names


## Table of Contents

* [Dependencies](#dependencies)
* [Usage](#usage)
* [Invocation](#invocation)
* [Customization](#customization)
* [Why?](#why)


## Dependencies

- `bash 4.0+`
- `coreutils`
    - File operations.
- `perl`
    - Used for non-greedy regex capturing.
- `sox`
    - For retrieving information about audio files (bitrate, duration, ...).
- `mid3v2`
- `metaflac`
- `vorbiscomment`
    - Optional. Programs for handling audio tags.

All of these should be readily available in most distributions.


## Usage

There are thre modes in `cursedtag` - file selector, editor & scanner.

* Selector mode:
   - **space** - mark/unmark selected file
   - **a, ctrl-a** - mark/unmark all files
   - **r** - rename files in scanner mode
   - **f** - fill tags in scanner mode
   - **→, enter, esc** - go to tag editor
   - **q, ctrl-c** - quit

* Editor mode:
   - **enter, a** - edit field (cursor at end)
   - **i** - edit field (cursor at start)
   - **s, w** - save changes to current file
   - **S, W** - apply field to all marked files
   - **u** - undo changed field
   - **←, esc** - go file selector
   - **q, ctrl-c** - quit

For moving around, you can use arrow keys, enter/escape, home/end, pgup/pgdown.

Few simple *vi*-like shortcuts are supported: *h/j/k/l*, *g* & *G*.

## Invocation

`$ cursedtag ~/Music`
 - Opens given directory in file selector mode.

`$ cursedtag ~/Music/file.mp3`
 - Opens the file in editor mode. The file selector is pointed to ~/Music.


## Customization

You can customize the program by setting following environment variables.

```sh
    # Space-separated list of tag field IDs
    # See mid3v2 -f for all frames. Note that not all frames are supported.
    CURSEDTAG_FIELDS=…

    # Value of this variable will be inserted
    # into prompts of file rename & fill tags modes.
    # For example "%n - %t"
    CURSEDTAG_DEFAULT_TEMPLATE=…

    # Override colors by assigning escape sequences into these variables.
    CURSEDTAG_COLOR_ERROR=…
    CURSEDTAG_COLOR_OPTION=…
    CURSEDTAG_COLOR_STATUS=…
    CURSEDTAG_COLOR_MARKED=…
    CURSEDTAG_COLOR_SUCCESS=…
    CURSEDTAG_COLOR_SELECTED=…
```


## Why?

*musophobia* ***(n.)*** <br />
  — a strong dislike of mice

hellricer [(<)](https://www.gnu.org/licenses/copyleft.en.html) 2019

