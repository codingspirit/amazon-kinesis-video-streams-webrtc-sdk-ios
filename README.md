
# The Amazon Kinesis Video WebRTC Sample With AK/SK
[![Build Status](https://travis-ci.org/awslabs/amazon-kinesis-video-streams-webrtc-sdk-ios.svg?branch=master)](https://travis-ci.org/awslabs/amazon-kinesis-video-streams-webrtc-sdk-ios)
[![Coverage Status](https://codecov.io/gh/awslabs/amazon-kinesis-video-streams-webrtc-sdk-ios/branch/master/graph/badge.svg)](https://codecov.io/gh/awslabs/amazon-kinesis-video-streams-webrtc-sdk-ios)

This sample demonstrates the Amazon KinesisVideoStreams and KinesisVideoSignaling framework found in the AWS Mobile SDK for iOS using access key/secret key without Cognito.

## Requirements

* Xcode 10 and later
* iOS 11 and later

#### Download the WebRTC SDK in iOS
To download the WebRTC SDK in iOS, run the following command:

    git clone https://github.com/awslabs/amazon-kinesis-video-streams-webrtc-sdk-ios.git
  

#### Using XCode to build the project

1. The AWS Mobile SDK for iOS is available through [CocoaPods](http://cocoapods.org). If you have not installed CocoaPods, install CocoaPods: (Requires Ruby installed) 

        sudo gem install cocoapods
        pod setup

2. To install the AWS Mobile SDK for iOS run the following command in the directory containing this sample:

        pod install

3. Open `KinesisVideoWebRTCDemoApp.xcworkspace` (File location: KVSiOS/Swift/AWSKinesisVideoWebRTCDemoApp.xcworkspace).

4. Add your AK/SK info into [ChannelConfigurationViewController.swift](https://github.com/codingspirit/amazon-kinesis-video-streams-webrtc-sdk-ios/blob/19c90e58fa7195ba4b504bbc4e92cb4d3ef9b14a/Swift/KVSiOSApp/ChannelConfigurationViewController.swift#L28):

```swift
    let accessKey = "REPLACE_ME"
    let secretKey = "REPLACE_ME"
```

5. To build and run, click the play button on the XCode menu. The following step-by-step instructions describe how to download, build, and run the Kinesis Video Streams WebRTC SDK in iOS.

#### Run the iOS Sample Application
Building the iOS sample application installs the AWSKinesisVideoWebRTCDemoApp on your iOS device. Using this app, you can verify live audio/video streaming between mobile, web and IoT device clients (camera). The procedure below describes some of these scenarios.

##### Note
*    Ensure that in all the cases described below, both the client applications use the same signaling channel name, region, viewer-id/client-id and the AWS account id.
*    Please note that a master should be started first before the viewer connects to it.

#####    Peer to Peer Streaming between two iOS devices: master and viewer:
*    Start one iOS device in master mode for starting a new session using a channel name (e.g. demo). Remote peer will be joining as viewer to this master.
*    Currently, there can be only one master for a channel at any given time.
*    Use another iOS device to connect to the same channel name (started up in the above step set up as a master) in viewer mode. This will connect to an existing session (channel) where a master was connected previously.

#####    Peer to Peer Streaming between [Embedded SDK](https://github.com/awslabs/amazon-kinesis-video-streams-webrtc-sdk-c) master and iOS device:
  *    Run KVS WebRTC embedded SDK (in C) in master mode on a camera device.
  *    Start the iOS device in viewer mode – you should be able to see the local video preview in the lower right side of the screen and also the larger part of the screen should stream the remote video view.

#####    Peer to Peer Streaming between iOS device as master and Web browser as viewer:
 *    Start one iOS device in master mode for starting a new session using a channel name (e.g. demo)
 *    Start the Web Browser using the Javascript SDK (JS with audio selected) and start it as viewer.
 *    Verify media showing up from the iOS device and also from the browser.

##### Note

* _This sample application has been tested in iPhone XS and iPhone 6._

## License
This library is licensed under the [Apache 2.0 License](https://github.com/awslabs/amazon-kinesis-video-streams-webrtc-sdk-ios/blob/master/LICENSE).
