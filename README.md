# quite-intriguing

## Find the right manpage or cheatsheet, easily.

![qi logo](https://raw.githubusercontent.com/uriel1998/quite-intriguing/master/qi-open-graph.png "logo")

![qi in action](https://raw.githubusercontent.com/uriel1998/quite-intriguing/master/example.gif "qi in action")
If the above is too small, you can see it on [terminalizer](https://terminalizer.com/view/c42ab47a4215)  

## Contents
 1. [About](#1-about)
 2. [License](#2-license)
 3. [Prerequisites](#3-prerequisites)
 4. [Installation](#4-installation)
 5. [Setup](#5-setup)
 6. [Usage](#6-usage)
 7. [TODO](#12-todo)

***

## 1. About

`quite-intriguing` (or `qi`) uses `fzf` to be able to search not only manpages but
your cheatsheets from `tldr` or `cheat` as well.  It also supplements the listings 
from the cheatsheets if there is a description in the manpages.

Its name and icon are meant to be an homage to the longrunning UK panel show 
["Quite Interesting"](https://qi.com/shows/qi) where you get to find out all sorts of interesting things; 
there is no connection express or implied between these files and that television program.

Except that it's good. Watch it.

## 2. License

This project is licensed under the MIT License. For the full license, see `LICENSE`.

## 3. Prerequisites

* [`fzf`](https://github.com/junegunn/fzf)
* `awk`, `sed`, `apropos`
* [`tldr`](https://github.com/tldr-pages/tldr)
* [`cheat`](https://github.com/rstacruz/cheatsheets)
* [`rofi`](https://github.com/davatorium/rofi) (OPTIONAL)

## 4. Installation

Put `quite-intriguing` and `quite-intriguing-preview` in the same directory where 
your shell can find them.  I created a symlink to the `quite-intriguing` file called 
just `qi`, or you can use an alias.  

## 5. Setup

It's recommended to run `quite-intriguing -p` before doing anything, and to re-run 
this command either as part of a cronjob or as a hook after installing a program via 
your package manager.  This allows the program to create its own little reference 
in `~/.config/qi_cachefile`. It not only reads in all the available entries from 
`man`, but also `tldr` and `cheat`.  As the latter two do not have descriptions 
as part of their UI, `qi` will match any filenames and enrich the descriptions. 

## 6. Usage

`quite-intriguing [OPTIONS] [SEARCHTERM]`

Omitting the search term is quite okay; including it just starts the search faster. 
Including a query assumes TUI mode (the default).

The various switches are:
    
* -h show help 
* -p Prefetch and compile options, then exit
* -r Rebuild available options (like -p) but then run
* -g GUI interface only. Default is CLI/TUI. This uses `rofi` instead of `fzf`. 

The gui display of results is a bit wonky for some reason and I can't figure 
out how to make it scroll properly. :/ If you know what I'm missing, I'd 
appreciate it.

## 7. TODO

* Fix GUI display of results
* Incorporate the previewer into the main script
* Figure out if there's a way to put short descriptions in cheatsheets 
