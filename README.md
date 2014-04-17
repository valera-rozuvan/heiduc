heiduc
======

Node.js YouTube batch audio downloader

Description
-----------

`heiduc` is a Node.js script which simplifies the task of
downloading a large number of videos from YouTube and extracting
audio tracks from them. `heiduc` is dependent on two very excellent
applications:

- [youtube-dl](http://rg3.github.io/youtube-dl): a small command-line
program to download videos from YouTube.com and a few more sites.
- [LAME](http://lame.sourceforge.net): LAME is a high quality MPEG
Audio Layer III (MP3) encoder.

Installing youtube-dl
---------------------

On a Debian based system:

    sudo apt-get install wget
    sudo wget https://yt-dl.org/latest/youtube-dl -O /usr/bin/youtube-dl
    sudo chmod a+x /usr/bin/youtube-dl

If there were no errors, try running:

    youtube-dl --version

The above command should print something along the lines of:

    2014.04.13

Installing LAME
---------------

If you are using Debian, make sure you have `non-free`, and `contrib`
archive areas enabled in your `/etc/apt/sources.list`. If you are not
familiar with Debian archive areas, please see
[Debian Policy Manual Chapter 2 - The Debian Archive](https://www.debian.org/doc/debian-policy/ch-archive.html). On a Debian based system:

    sudo apt-get install lame

If there were no errors, try running:

    lame --version

The above command should print something along the lines of:

    LAME 32bits version 3.99.5 (http://lame.sf.net)

Installing heiduc
-----------------

Clone this repository anywhere you like:

    sudo apt-get install git
    cd SOME_DIRECTORY
    git clone https://github.com/valera-rozuvan/heiduc.git

You are done!

Running heiduc
--------------

Make sure you have `node` installed. If not, please refer to
[Installing Node.js via package manager](https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager). Then:

    cd SOME_DIRECTORY/heiduc
    node heiduc.js file_with_links

The file `file_with_links` should contain YouTube video URLs, a single
URL on a single line. Example contents of such a file:

    https://www.youtube.com/watch?v=1U_sb_Z6LR0&list=PLB62D7326BF1A5BD9&shuffle=1411
    https://www.youtube.com/watch?v=4iF4Rn2b4T8
    https://www.youtube.com/watch?v=Az8ESdT3gZI&list=PLD8C4B198C8F6AB4E

The main thing to note is that each URL contains a sub-string like
`v=4iF4Rn2b4T8`. `4iF4Rn2b4T8` is a YouTube video ID. `heiduc` will download
a single video from a single URL. The video will be the one with the ID from
the URL.

General information
-------------------

Git is an Open Source project covered by the GNU General Public
License version 2. It was originally written by
<a href="http://valera.rozuvan.net/">Valera Rozuvan</a>.

Please read the file LICENSE for the full license information.
