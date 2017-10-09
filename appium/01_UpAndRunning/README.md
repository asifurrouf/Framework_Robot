## LINKS

* [Appium up & running with Robot Framework](http://testnblog.com/appium-up-running-with-robot-framework/)
* [Structure for Appium Test Cases – Robot Framework](http://testnblog.com/structure-for-appium-test-cases-robot-framework/)



### Appium up & running with Robot Framework

Appium is a client/server architecture.
Client is used to run the test cases.
Server is used to run the Appium Server.The mobile devices or the emulators are required to run the tests against the app which we are testing.
Client & Server mentioned above could be 2 different hosts or can be a same host. Currently in my setup, both client & server are installed in the same OSX host.

## Client Setup

* pip install robotframework
* pip install robotframework-appiumlibrary
* There are many text editors & IDEs we can use.

## Server Setup

* brew install node  >> get node.js
* npm install -g appium  >> get appium
* npm install wd >> get appium client
* appium & >> start appium
* netstat -an | grep 4723 >> netstat -an | findstr “4723"

## Android Path

* export ANDROID_HOME=/Users/shivaram/Documents/Android/sdk
* export PATH=${PATH}:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools

## device is ready for testing ?

* adb devices
* adb shell pm list packages -f
* netstat -an | grep 4723


