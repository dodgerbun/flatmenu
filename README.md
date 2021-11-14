# flatmenu

A simple stateless filesystem-based menu for dmenu and rofi allowing you to recursively navigate a directory of shortcuts or executables and launch what you land on. It is especially useful to throw on a keybinding for your WM to avoid coding custom menus with hierarchies. Simply make text files or shell scripts (or symlinks thereof) in ~/.menus (or wherever you specify with -m). Categorize with directories, your only limit is your filesystem's naming requirements.

Requirements: php (tested on 8.0.12)
dmenu or rofi, or other launcher that takes stdin split by newlines.

```text
flatmenu - display a menu from a directory of flat executable files

fill a directory with executables, shell scripts, etc and get
a simple choice which to run. The filename is your menu entry name and
its contents will be executed by the current user (if they have execute permission).
You can navigate directory structure as well. You will only be shown executable items.

usage:
flatmenu [-d] [-m menudir] [-h] [-e] [-x] [-l src -n name]
 -d - use dmenu instead of rofi (default: rofi if available, then dmenu)
 -m - use custom directory for menu
      menudir: default: /home/dodger/.menus, then /usr/bin
 -h - display this help and exit
 -e - generate example menu in /home/dodger/.menus and exit
 -x - set everything in menudir to executable (risky business) and exit.
 -l, -n - symlink src (must be absolute path, but supports ~) to name in the menu dir and exit
       ex. flatmenu -l ~/scripts/script.sh -n "Run my script plz"
```
