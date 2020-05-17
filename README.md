**Node.js wrapper for Un4Seen BASS Audio Library**

[BASS Audio library](http://www.un4seen.com) BASS is an audio library for use in software on several platforms. Its purpose is to provide developers with powerful and efficient sample, stream (MP3, MP2, MP1, OGG, WAV, AIFF, custom generated, and more via OS codecs and add-ons), MOD music (XM, IT, S3M, MOD, MTM, UMX), MO3 music (MP3/OGG compressed MODs), and recording functions. All in a compact DLL that won't bloat your distribution.

With the time, this wrapper aims to bring into Node.js all BASS functionalities, including all of their add-ons. Versions **0.9.x** are a technological refresh of the very well done [bassaudio](https://www.npmjs.com/package/bassaudio) wrapper developed by [doruk](https://www.npmjs.com/~doruk) and [serkamp](https://www.npmjs.com/~serkanp). The main reason for this is the lack of compatibility of some of the bassaudio wrapper dependencies (ffi, ref, ref-array and ref-struct) with the latest versions of Node.js.


**Compatibility**

Tested on Win x64 with Node (12.16.3), NPM (6.14.4) and BASS (2.4.15), BASSenc (2.4.14) and BASSmix (2.4.10). These are the only BASS add-ons supported by the original bassaudio wrapper.
All BASS binaries can be downloaded from the [BASS website](http://www.un4seen.com).


**BASSAUDIO original documentation**

For details on what BASS functions are implemented at the moment, plese refer to the original wrapper [NPM page](https://www.npmjs.com/package/bassaudio).


**CHANGE LOG**

- 0.9.1
	- Replaced dependencies into .json file
		- ✗	ffi (2.2.0) replaced with ✓ ffi-napi (2.5.0)
		- ✗ ref (^1.3.2) replaced with: ✓ ref-napi (2.0.0)
		- ✗ ref-array (^1.2.0) replaced with: ✓ ref-array-napi (1.2.1)
		- ✗ ref-struct (^1.1.0) replaced with: ✓ ref-struct-napi (1.1.1)
	
	- Updated the two dependendencies below
		- ✓ chalk (4.0.0, required ^1.1.3)
		- ✓ replace-in-file (6.0.0, required ^2.5.0)
	
	- Cleaned the original .gitignore
	
	- Updated referencies in:
		-	shim.js
		-	index.js
		
	-	Updateted readme.md

- 0.9.0
    Cloned the original bassaudio wrapper.
