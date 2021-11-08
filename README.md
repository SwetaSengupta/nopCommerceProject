# Selenium Hybrid Framework
### (Python, Selenium, PyTest, Page Object Model, HTML Reports)

eCommerce Application
https://www.nopcommerce.com/en/demo

Frontend

Backend  https://admin-demo.nopcommerce.com/login?ReturnUrl=%2Fadmin%2F


### Test Scenario


[![Screenshot-2021-11-07-151750.png](https://i.postimg.cc/25WtkgLy/Screenshot-2021-11-07-151750.png)](https://postimg.cc/kVnsw1cP)



### Packages/plugins used
1) Selenium: Selenium Libraries
2) Pytest : Pytest UnitTest framework
3) pytest-html: PyTest HTML Reports
4) pytest-xdist : Run Tests Parallel
5) Openpyxl : MS Excel Support
6) Allure-pytest: to generate allure reports


### Folder Structure(Framework)

Project Name
      |

pageObjects(Package)
     
      |

testCases(Package)

      |
utilities(Package)

      |
TestData(Folder)
     
      |
Configurations(Folder)

       |
Logs(Folder)
  
    |
Screenshots(Folder)

     |
Reports(Folder)

    |
Run.bat

### Automating Login Test Case

1. Create LoginPage Object Class under "pageObjects"
2. Create LoginTest under "testCases"
3. Create conftest.py under "testCases"

### Capture screenshot on failures
1.Update Login Test with Screenshot under "testCases"

### Read common values from ini file

1. Add "config.ini" file in "Configurations" folder
2. Create "readProperties.py" utility file under utilities package to read common data.
3. Replace hard coded values in Login test case.

### Adding logs to test case
1. Add customerLogger.py under utilities package.
2. Add logs to Login test case.

### Run Tests on Desired Browser/Cross Browser/Parallel
1. Update conftest.py with required Fixtures which will accept command line argument(browser).
2. Pass browser name as argument in command line

### To Run tests on desired browser
``pytest -s -v testCases/test_login.py --browser chrome``

``pytest -s -v testCases/test_login.py --browser firefox``

### To Run tests parallel
``pytest -s -v -n=3 testCases/test_login.py --browser chrome``

``pytest -s -v -n=3 testCases/test_login.py --browser firefox``

### Generate pytest HTML Reports
1. Update conftest.py with pytest hooks
2. To Generate HTML report run below command:
``pytest -s -v -n=3 --html=Reports\report.html testCases/test_login.py -- browser chrome``



