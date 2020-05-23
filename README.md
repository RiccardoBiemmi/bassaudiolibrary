**Node.js wrapper for Un4Seen BASS Audio Library**

[BASS Audio library](http://www.un4seen.com) BASS is an audio library for use in software on several platforms.

This project is to bring BASS power into Node.js, with all its features and including all of their add-ons, one by one, starting from the BASS Core library.

Version **0.9.2** is about cleaning the [bassaudio](https://www.npmjs.com/package/bassaudio) wrapper developed by [doruk](https://www.npmjs.com/~doruk) and [serkamp](https://www.npmjs.com/~serkanp).
After a first technological update - in order to make it and its dependencies compatible with the latest versions of Node.js - now it's time to clean the original code and decouple the core library from the two add-ons originally hard coded with it (BASSMix and BASSEnc).

This is a necessary step in view of the overall architectural re-design of the wrapper (versions **0.9.5** and beyond).

New functionalities, either filling the original wrapper gaps or including new BASS features and add-ons, will start from version **1.0.0**, following to the quick roadmap below.


**Compatibility**

Tested on Win (x64) with Node (12.16.3), NPM (6.14.4) and BASS (2.4.15).

All BASS binaries can be downloaded from the [BASS website](http://www.un4seen.com) and will not be provided with this wrapper. Examples of how to use the wrapper can be found in the [original wrapper repository](https://www.npmjs.com/package/bassaudio).


**BASSAUDIO original documentation**

For details on what BASS functions are implemented at the moment, plese refer to the original wrapper [NPM page](https://www.npmjs.com/package/bassaudio) for all **0.9.x** versions.
Starting from version **1.0.0** i will provide the list of implemented functions as part of [bassaudiolibrary documentation](https://codeartisan.riccardobiemmi.com/bassaudiolibrary/).

The original [BASS documentation](http://www.un4seen.com/doc/) sucks, really, a lot, so i will try to cover as much as i can in this wrapper documentation, starting from version **1.0.0**.


**EXAMPLES**

**Basic loading and playnig from file**
```javascript
const modBass = require( "bassaudiolibrary" );
const objBass = new modBass();

//	Init the output device. -1 is default output device
const bResult = objBass.BASS_Init( -1, 44100, objBass.BASS_Initflags.BASS_DEVICE_STEREO );
if( !result ) {
	console.log( "error init sound card:" + objBass.BASS_ErrorGetCode() );
}

//	Create the audio stream from a given file. Audio formats supported by the core BASS library: MP3, MP2, MP1, OGG, WAV, AIFF
const objChannel = objBass.BASS_StreamCreateFile( 0, "{YOUR AUDIO FILE FULL PATH HERE}", 0, 0, 0 );
if( objBass.BASS_ErrorGetCode() != objBass.BASS_ErrorCode.BASS_OK ) {
	console.log( "error opening file:" + objBass.BASS_ErrorGetCode() );
}

//	Play the audio stream on the initialized output device, restarting the channel (-1)
const bSuccess = objBass.BASS_ChannelPlay( objChannel, -1 );
if( !bSuccess ) {
	console.log( "error playing file:" + objBass.BASS_ErrorGetCode() );
}

///	Enjoy the song...

//	Free the memory after the audio has completely played
objBass.BASS_Free();
```


**ROADMAP**
- 0.9.3
	- Refactoring to improve ES9 compatibility
	- Validate the need to keep the original shim for [FFI](https://www.npmjs.com/package/ffi)
- 0.9.4
	- Implement bBasic plug-in mechanism to allow easy integration with BASS add-ons wrappers
- 0.9.5
	- Refactor all interfaces to map down to WEB Audio API architecture (for fall-back compatibility)
- 1.0.0
	- Full implementation of the BASS core library (currently v. 2.4.15)
- 1.1.0
	- Full implementation of the BASSEnc add-on (currently v. 2.4.14)
- 1.2.0
	- Full implementation of the BASS Tags add-on (currently v. 18.0)


**CHANGE LOG**

- 0.9.2
	- Architectural cleaning: decoupled BASS core from the add-ons supported in the original wrapper
	- Basic support for BASS core library only is now provided

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