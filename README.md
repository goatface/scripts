#My favorite shell scripts
This collection of scripts ranges from essentially one-liners to full blown HTML parsing scripts.

They only have an ephemeral relation to one another: they are all written by me, and they all live in $HOME/scripts on my computer

A description of each one is provided below, in alphabetical order
##getpaper
For a complete description, see http://www.cns.s.u-tokyo.ac.jp/~daid/hack/getpaper.html

Download, add bibtex, query bibtex, strip propaganda, print, and/or open papers based on reference!

Here, _papers_ are academic journal articles, usually somehow related to nuclear astrophysics, which is my interest.  It mainly relies on the [SAO/NASA Astrophysics Data System (ADS)](http://adsabs.harvard.edu/) and would typically take queries following the Journal/Volume/Page format.  In a full blown operation, here is what happens:
* You feed _getpaper_ some options, including a journal name, a volume, and a page number
* _getpaper_ checks if ADS has a matching query (and if there are multiple returns, prompts you to choose one)
* _getpaper_ checks if you have a matching bibkey in your library.bib file, so as not to duplicate
* _getpaper_ checks the expected output PDF file name, so as not to download for no reason
* If it was instructed to open the paper, it would open the paper you already had but forgot you downloaded
* Finding that you do not have this paper, it will generate a full bibtex entry, including the abstract
* _getpaper_ will download the paper (if you have subscription access)
* _getpaper_ will ensure that what was downloaded looks like a legitimate PDF and not rubbish
* _getpaper_ will link the downloaded location of the paper into the bibtex entry
* _getpaper_ will create a sensible directory structure like articles/2013 to place the paper if needed
* _getpaper_ will open the paper if you asked it to
* _getpaper_ will print the paper if you asked it to

If you didn't have subscription access, perhaps because you are at home or travelling...
* _getpaper_ can accept an SSH user and host to a machine at your work, and use that server to transparently download and transfer the paper to your local machine (though you should set up passwordless SSH and ensure your work machine has the right tools).

And it will do all that, with a simple, single command.  That could save you at least thirty or sixty seconds doing it yourself!

What it will not do:
* Harvest papers blindly.  You need to feed it the relevant Journal/Volume/Page information yourself.  This is to comply with the online journals' TOS.

##mplall
Loops over media files.  A low overhead, no-nonsense, single command to pilot mplayer or mplayer2.  I use it every day.

It loops forever, does full screen on video, can do alphabetic or random playlists starting from the present directory.  I never need more than this.

##vil
vi last or vi log.  If you often find yourself doing something like `ls -altr` to see recently modified files to open one in a text editor, this is for you.  Who wants to remember the name of recent log files, anyway?  Starting from the most recently modified, `vil` keeps asking if you want to open that file, cycling to the next, until you agree or kill it.

##viw
vi which, an easy way to open anything in your path, like a shell script.  It's faster than typing `vi $(which blah)` to type `viw blah`.
