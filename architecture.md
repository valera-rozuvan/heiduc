Architecture
============

The aim for the 1.0 `heiduc` release will be a simple working prototype.
The script will be split into 2 phases.

Phase 1
-------

1. Parse command line arguments.
2. See if first command line argument is a file that can be opened
for reading.
3. Open file, read all contents into memory, for each line creating
an entry that will contain:

  - full URL
  - YouTube video ID

Phase 2
-------

1. Loop over the entire list of entries.
2. For each entry:

  - get the title of the YouTube video
  - use `youtube-dl` shell command to get the YouTube video
  - use `ffmpeg` shell command to extract raw audio
  - use `lame` command to encode audio to MP3 format
  - rename the MP3 using the title of the YouTube video
  - clean up - remove video file, and raw audio file
