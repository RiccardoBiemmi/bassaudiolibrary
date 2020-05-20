**Node.js wrapper for Un4Seen BASS Audio Library**

[BASS Audio library](http://www.un4seen.com) BASS is an audio library for use in software on several platforms.

This wrapper aims to bring into Node.js all BASS functionalities, including all of their add-ons, one by one, starting from the BASS Core library.

Version **0.9.1** was about a technological refresh and cleaning of [bassaudio](https://www.npmjs.com/package/bassaudio) wrapper developed by [doruk](https://www.npmjs.com/~doruk) and [serkamp](https://www.npmjs.com/~serkanp). The main reason for first step is the lack of compatibility of some of the original bassaudio wrapper dependencies (ffi, ref, ref-array and ref-struct) with the latest versions of Node.js.

New functionalities, either filling the original wrapper gaps or including new BASS features and add-ons, will start from version **1.0.0**, following to the quick roadmap below.


**Compatibility**

Tested on Win (x64) with Node (12.16.3), NPM (6.14.4) and BASS (2.4.15), BASSenc (2.4.14) and BASSmix (2.4.10). BASSEnc and BASSmix are the only BASS add-ons supported by the original bassaudio wrapper and will be removed starting from version **0.9.2**.

All BASS binaries can be downloaded from the [BASS website](http://www.un4seen.com) and will not be provided with this wrapper.


**BASSAUDIO original documentation**

For details on what BASS functions are implemented at the moment, plese refer to the original wrapper [NPM page](https://www.npmjs.com/package/bassaudio) for all **0.9.x** versions. Starting from version **1.0.0** i will provide the list of implemented functions as part of [bassaudiolibrary documentation](https://www.riccardobiemmi.com/bassaudiolibrary/).


**ROADMAP**
- 0.9.2
	- Architectural cleaning: decoupled BASS core from the add-ons supported in the original wrapper
	- Implement (basic) support for BASS core library only
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
