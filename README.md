# dcrandroid - Decred Mobile Wallet
[![Build Status](https://travis-ci.org/raedahgroup/dcrandroid.svg?branch=master)](https://travis-ci.org/raedahgroup/dcrandroid)

A Decred Mobile Wallet for android that runs on top of [dcrwallet](https://github.com/decred/dcrwallet).

## Requirements:
Android 3.0 or above.

## Building dcrwallet
You can use the provided script or build it manually. Dcrwallet is required for this app to run, and has been modified to run as its own process. Dcrd is built to run as its own process for use with local full node mode. We use the [p2p-mobile](https://github.com/raedahgroup/dcrwallet/tree/p2p-mobile) branch of dcwallet that is based on the dcrwallet [p2p](https://github.com/jrick/btcwallet/tree/p2p) branch ([comparison](https://github.com/raedahgroup/dcrwallet/compare/p2p...p2p-mobile)). We use the [cf-mobile](https://github.com/raedahgroup/dcrd/tree/cf-mobile) branch of dcrd that is based on the [cf](https://github.com/jrick/btcd/tree/cf) branch ([comparison](https://github.com/raedahgroup/dcrd/compare/cf...cf-mobile)).

### Prerequisites
1. [Go(1.8 or 1.9)](http://golang.org/doc/install)
2. [Dep](https://github.com/golang/dep/releases)
3. [Gomobile](https://github.com/golang/go/wiki/Mobile#tools)

To compile, navigate to the dcrandroid clone directory and run
    
    ./build.sh
Or run the following commands

    go get -v github.com/decred/dcrwallet
    cd $GOPATH/src/github.com/decred/dcrwallet
    git fetch https://github.com/raedahgroup/dcrwallet p2p-mobile
    git branch p2p-mobile FETCH_HEAD
    git checkout p2p-mobile
    dep ensure -v
    gomobile bind -target=android/arm

## Building the android app
Android Studio(or gradle) and Android SDK is required to compile.

### Prerequisites
1. [Android Studio](https://developer.android.com/studio/index.html)
1. [Gradle](https://docs.gradle.org/current/userguide/installation.html)
2. [Android SDK](https://developer.android.com/sdk/download.html) with build tools 26.0.2, SDK Platform 27 and Android support repository installed

Clone dcrandroid (or fork it):

    git clone https://github.com/raedahgroup/dcrandroid.git

### Building with Android Studio (Recommended)
* Open Android Studio
* Select `import project`
* Navigate to dcrandroid clone directory and click `OK`
### Building with Gradle Command Line
On Mac OS or Linux, open terminal and navigate to dcrandroid clone directory, then run:

    ./gradlew
On a Windows PC, open command prompt and navigate to the dcrandroid clone directory, then run:
    
    gradlew.bat
