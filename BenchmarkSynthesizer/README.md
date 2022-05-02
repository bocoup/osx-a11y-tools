# Introduction

This is a speech synthesis voice for OSX. It does not output any audio, instead it sends TCP messages when speech requests are made.

## Installation

Run `sudo xcodebuild install DSTROOT=/`
Then run `sudo pkill -f com.apple.speech.speechsynthesisd`

## Usage

1. Set up a local TCP server listening on port 4449.
1. Set speech output to Cher.
1. All speech requests will be sent as TCP messages to the local server.

## Packaging

To create a package suitable for installation in another macOS environment
(macOS 10.15 or later):

1. **Download the Mac OSX 10.15 SDK** - this is included in Xcode 11.7 and can
   be downloaded from Apple using a valid AppleID using [the link maintained
   here](https://github.com/devernay/xcodelegacy))
2. **Install the SDK** - expand the `.xip` file and move the SDK directory to
   the Xcode application's "developer platform" directory, e.g. via the
   following command:

       mv ./SDKs/MacOSX10.15.sdk /Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/
3. **Build the package** - run the following command:

       make
