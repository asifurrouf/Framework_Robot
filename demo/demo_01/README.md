### [Introduction](https://bitbucket.org/robotframework/cdemo)

This simple example demonstrates how to use C language from Robot Framework test libraries. The example uses Python's standard ctypes module, which requires that the C code is compiled into a shared library. This version is implemented and tested on Linux, but adapting it to other operating systems would require only changing compilation and name of the produced shared library.
If you are mainly interested to learn how to create tests cases for Robot Framework or how to extend it with custom libraries, you should probably study other documentation and demo projects instead.

### Contents:

    Downloading demo package
    System under test
    Test library
    Test cases
    Running tests
    Generated results


### Downloading demo package:

The latest demo package is available on the project downloads as CDemo-<date>.zip. After downloading and unzipping the package, you should have all the files in a directory CDemo.
All the files related to the demo as well as the generated results are also available online. There is thus no need to download the demo if you are not interested in running tests yourself.


### System under test

The demo application is a very simple login system (login.c), that validates the given user name and password and returns the status. There are two valid username password combinations: demo/mode and john/long.
Before running the demo, you need to compile the demo application by simply running make in the directory that was created when you extracted the demo package. This will create shared library liblogin.so.

### Test library

LoginLibrary.py is a simple test library that can interact with the system under test using the ctypes module. The library provides only one keyword Check User.
The if __name__ == '__main__' block in LoginLibrary.py is not used by the executed tests, but it allows using the library code as a tool for manual testing. You can test this handy behavior on the command line:

python LoginLibrary.py demo mode
python LoginLibrary.py demo invalid


### Test cases

The login_tests.robot test case file contains all tests for this demo. 
It contains separate tests for valid and invalid login.

### Running tests

* pip install robotframework
* robot --help
* robot login_tests.robot

### Generated results

After running tests you will get report and log in HTML format. 
Example files are also visible online in case you are not interested in running the demo yourself:

    report.html
    log.html





