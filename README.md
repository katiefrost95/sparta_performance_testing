# Sparta_performance_testing

The repository contains performance tests for a variety of apis. This is my first practice at writing performance tests.
Performance testing includes load, spike, stress, soak testing.

Links to the API's tested:

NASA Neows API - https://api.nasa.gov/api.html#NeoWS
OpenWeather API - https://openweathermap.org/api
Postcodesio API- http://postcodes.io/


To run the tests you need to install Jmeter. This is the documentation for downloading Jmeter - http://jmeter.apache.org/download_jmeter.cgi.

**How to write test plan in Jmeter**
First create a threadgroup by right clicking on the test plan - Add - Thread - Threadgroup.
In the threadgroup:
right click- add-config element- HTTP Request Default
right click- add-config element- HTTP Header Manager
right click- add-sample- HTTP Request
right click- add-listerners-view results tree
right click- add-sampler- debug sampler
right click- add-listeners- summary report


Inside HTTP request:
right click- add - assertion- response assertion
right click- add - post processor - JSON Extractor

In the Test Plan you declare your variables.
The thread group is used to put the conditions for your tests, eg number of users: 100, Ramp up Period: 1 second, Forever: 1 - This would be a spike test.
In HTTP request defaults you put http and source of the website url.
in HTTP header manager you put the type it is for example: name - content-type, value - Application/Json
In HTTP Request you input the path of the part of the website you want to test and whether it is a post or get request etc.
The JSON Extractor is used to get back specific data in the JSON.
The response assertion is used to check a specific item is in the data.
The results tree is where you see the results of the data.
