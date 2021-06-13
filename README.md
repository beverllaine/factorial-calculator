## Exploratory Test Report : Factorial Calculator Assessment:

Pre-Req: value input https://en.wikipedia.org/wiki/Factorial

<b>AC1: PASSED with Concern</b></br>
```gherkin
Given http://qainterview.pythonanywhere.com/ is open
When page  loaded successfully
Then Title bar name should be Factorial
```
Bug1: Double 'l' in name Factorial. </br>
Bug2: No logo or icon (if factorial name represents a company app there should be)</br>
Artifact: http://g.recordit.co/VoCEr79Juw.gif</br>

<b>AC2: PASSED</b></br>
```gherkin
When page loaded successfully</br>
Then 'The greatest factorial calculator!' should be seen.
And placeholder in textfield 'Enter an integer' should be seen
And green button 'Calculate!' should be seen.
```
Artifact: http://g.recordit.co/VoCEr79Juw.gif</br>

<b>AC3: PASSED with Concern</b></br>
```gherkin
When Factorial loaded successfully</br>
And User enters positive integer from 0-10^100</br>
And reload the page</br>
Then placeholder text should be seen.</br>
```
Bug3: Page reloaded successfully however, textfield input value was retained.</br>
Artifact: http://g.recordit.co/VoCEr79Juw.gif</br>

<b>AC4:PASSED with Concern</b></br>
```gherkin
When Factorial loaded successfully
And User enters positive integer from 0-10^100
Then 'The factorial of X is: Y' should be seen. (X= integer input; Y=calculated value)
```
Bug3: 'Infinity' was result displayed when input integer: 450. Also noticed a non integer that is greater than 450, UI doesnt response. Upon checking console it shows '500
INTERNAL SERVER ERROR'</br>
Artifact: http://g.recordit.co/Ez4ALSFEyz.gif</br> 

<b>AC5: PASSED</b></br>
```gherkin
When Factorial loaded successfully
And User inputs a  positive or negative decimal number 
Then Error message should be seen.
```
Artifact: http://g.recordit.co/e9awBFKv9I.gif</br>

<b>AC6: PASSED with Concern</b></br>
```gherkin
When Factorial loaded successfully
And User inputs negative integer number 
Then Error message should be seen.
```
Bug4: No error message displayed for invalid input.</br>
Artifact: http://g.recordit.co/e9awBFKv9I.gif</br>

<b>AC7: PASSED with Concern</b></br>
```gherkin
When Factorial loaded successfully
And User clicks any textlink Privacy or Terms and Conditions
Then User should be redirected to appropriate screen content.
```
Bug5: HTML text is shown This is the X document. We are not yet ready with it. Stay tuned!</br>
Artifact: http://g.recordit.co/dsfBrc9GeA.gif

### Other Questions
<b>What behavior would you check if you had an extra hour to test?</b>
```
I believe covered the happy path and the negative path for the functionality test to ensure the apps works. 
And I wouldn't trade the quality of testing the scenarios over speed which might cause major issue in Production in reality. But still mindful on the project timeline.
```
<b>How would you automate testing of this application? What (software) tools would you use?</b>
```
I would automate this application using Robot Framework Selenium library and or Python(but disclaimer im still learning python programming.)
```
<b>Imagine you had to design a process for your team to make sure this application was tested well each week. How would you design this? What tools would you use?</b>
```
1. We need to categorize stories or features that are need for manual testing and which can be directly automate (in parallel with the developers working on the feature) atleast draft automated test or  prepare element locator name.  
2. Any QA can grab the story and can draft automated test. Once the feature is in staging, then QA can proceed or update their automated test and should indicate an appropriate test tag. 
3. Test tags like Smoke or Regression are scheduled test which will be run every X time of any day. (For feature monitoring purposes, once all are set in or released in PROD)

Tools
1. Github Actions and setting up of Workflow.(But would need help from Infra dev to do setup process of build/integrate/test)
2. Selenium Library using RobotFramework 
```
