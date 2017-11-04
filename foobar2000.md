# How to name and tag audio files

1. Rename track files to be in proper order (right click menu->File Operations->Rename to->My rename):
```
[%discnumber%_]%tracknumber% - [%track artist% - ]%title%
```

2. Try to fill tags automatically from https://musicbrainz.org/, using release ID copied from URL after searching album manually

3. Edit following tags in every audio file (right click menu->Properties):

* Artist Name - for classical genre put "Composer" there
* Artist Sort - from "Artist Name", in form `<Last Name>, <all others names>`
* Track Title
	* use Clean Up function
	* Capitalize all words in titles except "a", "an", "the", "at", "by", "for", "in", "of", "on", "to", "up", "and", "as", "but", "it", "or", "nor"
* Track Title Sort - from "Track Title", in form `<rest of title>, <one of values "The", "A", "An", "Der", "Die", "Das", "Ein", "Eine", "El", "Los", "La", "Las", "Un", "Unos", "Una", "Unas", "Le", "Les", "Une", "Des")`
* Album Title - use Clean Up function
* Album Title Sort - from "Album Title", in form `<rest of title>, <one of values "The", "A", "An", "Der", "Die", "Das", "Ein", "Eine", "El", "Los", "La", "Las", "Un", "Unos", "Una", "Unas", "Le", "Les", "Une", "Des")`
* Date - year of original song release
* Genre - according to musicbrainz.org
* Composer - applicable only for classical music
* Performer - applicable only for classical music
* Album Artist - in case of single artist album identical to "Artist Name", otherwise "Various Artists"
* Album Artist Sort - from "Album Artist", in form `<Last Name>, <all others names>`
* Track Number - without leading zero
* Total Tracks
* Disc Number - only if more than 1
* Total Discs - only if more than 1
* Comment - song review from AMG or other long text
* Lyrics - try to find lyrics using foobar extensions or manually
* Cover Art - standard resolution 500x500 px, best source is allmusic.com or amazon.com
	
4. Put any files other than tracks into directory called `_info`, name files using following patterns:
* `00_notes.txt` put any text info into this file including source URLs (usually allmusic.com and amazon.com)
* `nn_<scan_description>` put any scans of covers and booklets, nn is ordinal number (01, 02, 03...), scan_description should adhere to followning pattern and order:
	* `box_front`
	* `box_back`
	* `slipcase_front`
	* `slipcase_back`
	* `cover_front`
	* `cover_back`
	* `traycard_out`
	* `traycard_in`
	* `disc`
	* `booklet_nn`
	* `sticker_nn`
	
5. Rename track files and move them to music directory (right click menu->File Operations->Move to->preset name as follows):
	- for classical genre use "classical" preset (%genre%\%ALBUMARTISTSORTORDER%\%ALBUMSORTORDER%\[%discnumber%_]%tracknumber% - [%track artist% - ]%title%)
	- for any other genre use "default" preset (%genre%\%ALBUMARTISTSORTORDER%\'['%date%']' %ALBUMSORTORDER%\[%discnumber%_]%tracknumber% - [%track artist% - ]%title%)
	- for Plex use one of options below:

```
\\zabka_nas\Music\<Album Artist> - <Album>\$IsNull(<Disc#>,,CD$Pad(<Disc#>,2)\)<Track#> - $If(<Artist>=<Album Artist>,,<Artist>" - ")$Sort(<Title>)
\\zabka_nas\Jazz\<Album Artist> - <Album>\$IsNull(<Disc#>,,CD$Pad(<Disc#>,2)\)<Track#> - $If(<Artist>=<Album Artist>,,<Artist>" - ")$Sort(<Title>)
\\zabka_nas\Classical\<Album Artist> - <Album>\$IsNull(<Disc#>,,CD$Pad(<Disc#>,2)\)<Track#> - $If(<Artist>=<Album Artist>,,<Artist>" - ")$Sort(<Title>)
```  
