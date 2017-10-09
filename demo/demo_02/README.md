### [Web testing](https://bitbucket.org/robotframework/webdemo) with Robot Framework and SeleniumLibrary

Robot Framework is a generic open source test automation framework and SeleniumLibrary is one of the many test libraries that can be used with it. In addition to showing how they can be used together for web testing, this demo introduces the basic Robot Framework test data syntax, how tests are executed, and how logs and reports look like.



### Contents:

    Downloading demo package
    Demo application
    Test cases
    Generated results
    Running demo


### Downloading demo package

To get the demo, you can either download and extract the latest WebDemo-<date>.zip package from the download page or checkout the source code directly. As a result you get WebDemo directory with demoapp and login_tests sub directories.
Example test cases and generated results are available also online. There is thus no need to download the demo if you are not interested in running it yourself.

### Test Cases:

* valid_login.robot

    A test suite with a single test for valid login.This test has a workflow that is created using keywords in the imported resource file.
    
* invalid_login.robot

    A test suite containing tests related to invalid login.These tests are data-driven by their nature. They use a single keyword, specified with the Test Template setting, that is called with different arguments to cover different scenarios.
    This suite also demonstrates using setups and teardowns in different levels.
    
* gherkin_login.robot
    
    A test suite with a single Gherkin style test.This test is functionally identical to the example in the valid_login.robot file.

* resource.robot

    A resource file with reusable keywords and variables.The system specific keywords created here form our own domain specific language.They utilize keywords provided by the imported SeleniumLibrary.


### Generated results

After running tests you will get report and log in HTML format. Example files are also visible online in case you are not interested in running the demo yourself:

    report.html
    log.html

## Commands

* pip install robotframework
* pip install robotframework-seleniumlibrary
* Starting demo application : python demoapp/server.py
* After the demo application is started, it is be available in URL http://localhost:7272. You can test it manually, valid credentials are demo/mode, and it needs to be running while executing the automated tests.
* If the application was started by double-clicking demoapp/server.py file, it can be shut down by closing the opened window. If it was executed from the command line, using Ctrl-C is enough.
* Running tests : robot login_tests
* You can also run an individual test case file and use various command line options supported by Robot Framework:
    robot login_tests/valid_login.robot
    robot --test InvalidUserName --loglevel DEBUG login_tests
*  Using different browsers: The browser that is used is controlled by ${BROWSER} variable defined in resource.robot resource file.
   robot --variable BROWSER:Chrome login_tests
   robot --variable BROWSER:IE login_tests 
    
