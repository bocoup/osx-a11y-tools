# Introduction

This is a speech synthesis voice for OSX. It does not output any audio, instead it sends http requests when speech requests are made. This is to allow better benchmarking of VoiceOver performance.

## Installation

Run `sudo xcodebuild install DSTROOT=/`
Then run `sudo pkill -f com.apple.speech.speechsynthesisd`

## Usage

1. Set up a local http server listening on port 8080.
1. Set speech output to Cher.
1. All speech requests will be sent as HTTP GET requests to the local server.

## Packaging

To create a package suitable for installation in another macOS environment
(macOS 10.15 or later):

1. Install the Mac OSX 10.15 SDK (this is included in Xcode 11.7 and can be
   download from Apple using a valid AppleID using [the link maintained
   here](https://github.com/devernay/xcodelegacy))
2. run the following command:

    make
