# rofitr

A bash script to translate text using rofi.

![rofitr](https://pub.yusufaktepe.com/git/rofitr.gif "rofitr in action")

## Usage
<table>
<tbody>
<tr><th colspan="2"><strong>Translation</strong></th></tr><tr><td><strong>Input</strong></td><td><strong>Description</strong></td></tr>
<tr><td><code>en:es text</code></td><td>Override default SOURCE and TARGET</td></tr>
<tr><td><code>:en text</code></td><td>Auto-detect SOURCE; translate into English</td></tr>
<tr><td><i>text</i></td><td>Translate with defaults</td></tr>
<tr><th colspan="2"><strong>Actions</strong></th></tr><tr><td><strong>Keyword</strong></td><td><strong>Description</strong></td></tr>
<tr><td><code>!e word</code></td><td>show examples for "word"</td></tr>
<tr><td><code>!s text</code></td><td>speak the "text"</td></tr>
<tr><td><code>!!</code></td><td>show last translation</td></tr>
<tr><td><code>!!e</code></td><td>show examples for last translation</td></tr>
<tr><td><code>!!s</code></td><td>speak last translation</td></tr>
<tr><td><code>!</code></td><td>select and translate from history</td></tr>
<tr><td><code>!d</code></td><td>select and delete from history</td></tr>
<tr><td><code>!dd</code></td><td>clear history (in delete mode)</td></tr>
</tbody>
</table>

#### Command line:
- Launch rofitr:
```
$ rofitr
```
- Translate into Russian:
```
$ rofitr :ru text
```
- Translate from primary selection (clipboard):
```
$ rofitr -s
```

## Requirements
* [rofi](https://github.com/davatorium/rofi)
* [crow-translate](https://github.com/crow-translate/crow-translate)
* Basic Linux utilities

## Configuration
Edit script to change default translation options or pass them from command line:
```
SOURCE=en TARGET=ru rofitr
```
Following options are configurable:
```
## Set defaults
# SOURCE="en"               # source language code
# TARGET="es"               # translation language code
# ENGINE="google"           # google, yandex or bing
# LOCALE="en"               # translator language ($LANG var. by default)
# SPEAK_SOURCE="false"      # speak the source (true/false)
# SPEAK_TRANSLATION="false" # speak the translation (true/false)

## Rofi general options
# leave these empty or comment out to use system defaults:
FONT="mono 10"
WIDTH="60"
LOCATION="2"
YOFFSET="20"

# use alternative config and theme
# CONFIG="~/.config/rofi/translate-config.rasi"
# THEME="/usr/share/rofi/themes/lb.rasi"

## Rofi required options
HIST_LINES="15" # lines to show for history mode
RES_LINES="42"  # limit output to screen height
PROMPT_TR=" translate"
PROMPT_HIST=" history"
PROMPT_DEL=" delete"
CLR_RESULT="#ebdbb2"    # text color for translation
CLR_HELP_HLBG="#b8bb26" # help mode highlight background
CLR_HELP_HLFG="#1d2021" # help mode highlight foreground
```
