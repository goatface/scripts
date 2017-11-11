#My favorite shell scripts
This collection of scripts ranges from essentially one-liners to full blown HTML parsing scripts.

They only have an ephemeral relation to one another: they are all written by me, and they all live in $HOME/scripts on my computer

A description of each one is provided below, in alphabetical order

##getpaper
getpaper has been moved to [its own home](https://github.com/goatface/getpaper)

##mkdbjail
Makes a chroot jail ('sandbox') for DropBox.  **It is assumed to be run by root or sudo.**

It's designed for Gentoo, but probably could work fairly easily on most GNU/Linux systems.  I'm not personally a huge fan of DropBox, but I've been known to use it from time to time when my own server is being pesky.  I'm also not a fan of proprietary software.  Secret proprietary software whose main function is to manipulate my personal files sounds really dangerous to me.  As a result, I stick it into a chroot jail so that, almost no matter what they have going on inside that black box, all that can happen is to bork its own playground.

Definitely not what I'd call _one of my favorite shell scripts_ since I don't use it too often.  But the wiki page was not only fairly erroneous before I made this, but so tedius mostly with commands to copy-and-paste.  I recently re-installed my distro, so I'll be doing this again at some point, whence I will take a look at this, update, and possibly improve it.  I think it was literally living only on the Discussion page on the Gentoo wiki, so it might get a larger audience here.

What the script does **not** do:
- install jail (but it had depcheck)
- useradd (simple enough anyway, and I don't want a script that makes users on someone's machine)
- Make the handy little dropbox shell script to cd .dropbox-dist && ./dropboxd
(Need to move dropboxd script to this repo...please wait!)
Otherwise it should do everything else. 

There could be like one permission mistake or something.  
It is only for 32-bit since I have no 64-bit system to test on. Please change the environment variables at the top to suit you 

The verbosity of output could be truncated, or in the best case done with tee or something into a log file. 

##mplall
Loops over media files, kind of like `cp -r *` if you could do `mplayer -r *`.  A low overhead, no-nonsense, single command to pilot mplayer or mplayer2.  I use it every day.

It loops forever, does full screen on video, can do alphabetic or random playlists starting from the present directory.  I never need more than this.  Probably you want your media organized by directories (Album/Arist/01. Song) and not a giant torrent dump with thousands of files in one directory.

Also, if you want to view nefarious files with more subterfuge, the only history that you did will be `cd` commands in your shell history!

##vil
`vil` functionally means _vi last_  (or _vi log_ in practice).  

If you often find yourself doing something like `ls -altr` to see recently modified files to open one in a text editor, this is for you.  Who wants to remember the name of recent log files, anyway?  Starting from the most recently modified, `vil` keeps asking if you want to open that file, cycling to the next, until you agree or kill it.

##viw
`viw` stands for _vi which_, an easy way to open anything in your path, like a shell script.  It's faster than typing `vi $(which blah)` to type `viw blah`.

Improves your ability to read binary or hex in a text editor...

##xscreensaver_toggle
I'm going to guess the name says it all.  In case you can't immediately get the point of this one...

`xscreensaver_toggle` will toggle xscreensaver from single mode to off mode (or vice versa).  This is because different pieces of software on GNU/Linux don't always play nice with each other.  Sure, if you're using [xine's UI](https://www.xine-project.org) unbeknownst to you it makes use of phantom Scroll Lock key presses to keep the movie visible (hey, at least _someone's_ using that key).  But if you're like me and usually using mplayer, there's really no good solution I've found, including heartbeat signals, to properly disable the screen saver.  And I get really sick of opening up the Demo tool all the time.  So, with this script, make a key shortcut and it will easily toggle your screen saver and inform you!
