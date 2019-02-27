<p align="center">
  <h3 align="center">cursedtag</h3>

  <p align="center">
        A console ID3 tag editor.
  </p>

  <p align="center">
        <a href="https://asciinema.org/a/qvNlrFrGB3xKZXb6GkremjZNp" target="_blank">
          <img src="./screenshot.png" width="80%" alt="cursedtag in action"/>
        </a>
  </p>
<br>

- Works in terminal / console.
- Tiny (written in *bash*, using few external utilities)
- Inspired by [EasyTAG's](https://github.com/GNOME/easytag) features
  and [cursetag's](https://github.com/lotuskip/cursetag) look.
- Can operate on multiple files:
  - apply field to all selected files
  - bulk rename files based on tags
  - fill tags from file names
- Customizable.


## Table of Contents

* [Dependencies](#dependencies)
* [Usage](#usage)
* [Invocation](#invocation)
* [Customization](#customization)
* [Acknowledgements](acknowledgements)
* [Why?](#why)


## Dependencies

- `bash 4.0+`
- `coreutils`
    - File operations.
- `perl`
    - Used for non-greedy regex capturing
- `sox`
    - For retrieving information about audio files (bitrate, duration, ...)
- `mid3v2`
    - Program handling (*ID3 tags*).

All of these should be readily available in most distributions, likely already installed.


## Usage

There are thre modes in `cursedtag` - file selector, editor & scanner.

* Selector mode:
   - **space** - mark/unmark selected file
   - **ctrl-a** - mark/unmark all files
   - **e, enter** - editor mode
   - **r** - rename files in scanner mode
   - **f** - fill tags in scanner mode
   - **q, esc, ctrl-c** - quit

* Editor mode:
   - **enter, a** - edit field (cursor at end)
   - **i** - edit field (cursor at start)
   - **s, w** - save changes
   - **S, W** - apply field to all marked files
   - **u** - undo changed field
   - **esc** - go back to file selector
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
    # Space-separated list of tag field IDs (plus the 'filename' literal).
    # See mid3v2 -f for all frames.
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

