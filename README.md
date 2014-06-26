#My favorite shell scripts
This collection of scripts ranges from essentially one-liners to full blown HTML parsing scripts.

They only have an ephemeral relation to one another: they are all written by me, and they all live in $HOME/scripts on my computer

A description of each one is provided below, in alphabetical order
##getpaper
For a complete description, see [my hompage](http://www.cns.s.u-tokyo.ac.jp/~daid/hack/getpaper.html).

Download, add bibtex, query bibtex, strip propaganda, print, and/or open papers based on reference!

Here, _papers_ are academic journal articles, usually somehow related to nuclear astrophysics, which is my interest.  It mainly relies on the [SAO/NASA Astrophysics Data System (ADS)](http://adsabs.harvard.edu/) and would typically take queries following the Journal/Volume/Page format.  In a full blown operation, here is what happens:
* You feed `getpaper` some options, including a journal name, a volume, and a page number
* `getpaper` checks if ADS has a matching query (and if there are multiple returns, prompts you to choose one)
* `getpaper` checks if you have a matching bibkey in your library.bib file, so as not to duplicate
* `getpaper` checks the expected output PDF file name, so as not to download for no reason
* If it was instructed to open the paper, it would open the paper you already had but forgot you downloaded
* Finding that you do not have this paper, it will generate a full bibtex entry, including the abstract
* `getpaper` will download the paper (if you have subscription access)
* `getpaper` will ensure that what was downloaded looks like a legitimate PDF and not rubbish
* `getpaper` will strip the first page of the PDF if it's nonsense about the online journal with your IP address
* `getpaper` will link the downloaded location of the paper into the bibtex entry
* `getpaper` will create a sensible directory structure like articles/2013 to place the paper if needed
* `getpaper` will open the paper if you asked it to
* `getpaper` will print the paper if you asked it to

If you didn't have subscription access, perhaps because you are at home or travelling...
* `getpaper` can accept an SSH user and host to a machine at your work, and use that server to transparently download and transfer the paper to your local machine (though you should set up passwordless SSH and ensure your work machine has the right tools).

**And it will do all that, with a simple, single command.**  That could save you at least sixty seconds doing it yourself!

What it will **not** do:
* Harvest papers blindly.  You need to feed it the relevant Journal/Volume/Page information yourself.  This is to comply with the online journals' TOS.  It keeps you from clicking the mouse, not from connecting to the internet ever again by downloading the Library of Alexandria.

You probably want to be using [JabRef](http://jabref.sourceforge.net/) to manage your library.bib file.  It's awesome...

##mplall
Loops over media files, kind of like `cp -r *` if you could do `mplayer -r *`.  A low overhead, no-nonsense, single command to pilot mplayer or mplayer2.  I use it every day.

It loops forever, does full screen on video, can do alphabetic or random playlists starting from the present directory.  I never need more than this.  Probably you want your media organized by directories (Album/Arist/01. Song) and not a giant torrent dump with thousands of files in one directory.

Also, if you want to view nefarious files with more subterfuge, the only history that you did will be `cd` commands in your shell history!

##vil
`vil` functionally means _vi last_  (or _vi log_ in practice).  If you often find yourself doing something like `ls -altr` to see recently modified files to open one in a text editor, this is for you.  Who wants to remember the name of recent log files, anyway?  Starting from the most recently modified, `vil` keeps asking if you want to open that file, cycling to the next, until you agree or kill it.

##viw
`viw` stands for _vi which_, an easy way to open anything in your path, like a shell script.  It's faster than typing `vi $(which blah)` to type `viw blah`.

Improves your ability to read binary or hex in a text editor...

##xscreensaver_toggle
I'm going to guess the name says it all.  In case you can't immediately get the point of this one...

`xscreensaver_toggle` will toggle xscreensaver from single mode to off mode.  This is because different pieces of software on GNU/Linux don't always play nice with each other.  Sure, if you're using [xine's UI](https://www.xine-project.org) unbeknownst to you it makes use of phantom Scroll Lock key presses to keep the movie visible (hey, at least _someone's_ using that key).  But if you're like me and usually using mplayer, there's really no good solution I've found, including heartbeat signals, to properly disable the screen saver.  And I get really sick of opening up the Demo tool all the time.  So, with this script, make a key shortcut and it will easily toggle your screen saver and inform you!.
