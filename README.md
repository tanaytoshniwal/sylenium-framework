[![Build Status](https://api.travis-ci.org/symonk/selenide-testng-allure2-test-automation-framework.svg?branch=master)](https://travis-ci.org/symonkselenide-testng-allure2-test-automation-framework)
[![MIT License](http://img.shields.io/badge/license-MIT-green.svg)](https://github.com/symonk/selenide-testng-allure2-test-automation-framework/blob/master/LICENSE)
![Free](https://img.shields.io/badge/free-open--source-green.svg)
[![Sonar Quality Gate](https://sonarcloud.io/api/project_badges/measure?project=io.symonk.github%3Aselenide-framework&metric=alert_status)](https://sonarcloud.io/dashboard?id=io.symonk.github%3Aselenide-framework)


## Selenide-TestNG-Allure2-Framework :flags:

The aim of this project is simple, provide a powerful test automation harness for testing web applications with java.  Because test automation (especially) at the ui layer is plagued with bad practice
I would like to start by outlining a few things of what **NOT** to use this harness for.  If such a license existed that would ban you from doing the following, I would apply it to this repository...

---

### :crossed_flags: Writing pointless short tests :crossed_flags:

This framework should be used to test end to end flows of your application under no isolation of the stack.  Writing tests for simple ui
functionality such as buttons being clickable, dropdown having values etc should be done by component tests.  Modern frameworks make this a piece of cake (angular, react etc).

---

### :crossed_flags: Only automating at the ui layer :crossed_flags:

Using this test automation harness as your only automated tests.  Focus on unit and integration tests as a primary method of coverage.

---

### :crossed_flags: Writing garbage locators :crossed_flags:

Using google chrome `copy-as-xpath` and using it directly etc.  Favour adding unique identifiers to your frontend to aid with automation.  `data-` attributes etc can be extremely useful.
Using complex xpaths will end in hassle later, and please account for the page state being different later with parallel tests running.  Your useless xpath locator finding row 3 in a table wont 
work later when 10 parallel tests have flooded the table data!

---

### :crossed_flags: Overcomplicating page objects :crossed_flags:

The beauty of this framework is we have **NO** driver or page factory code in our page objects, its all handled behind the scenes using custom reflection and java dynamic properties, coupled with smart webdriver management.
Keep your page objects simple, exposing a fluent interface for the tests to consume.  Always remember a page object is **NOT** equal to a page `!=`.  A page object can encapsulate a simple
dropdown on a page, which can be injected or reused as part of another page object.  `KISS`.

---

### :crossed_flags: Managing test data poorly :crossed_flags:

Managing test data using this harness itself through the ui for example, terrible practice.  Hopefully you have or can get access to some cool restful services to help you manage the data.  Managing test data
is most certainly not easy and becomes a behemoth over time.  The debate of randomising data is a long going one.  Please dont use your browsers for prepping and tearing down test data.  I don't even like direct database manipulation either,
from experience you will spend too long doing maintenance.

---

### :crossed_flags: Running sequential tests :crossed_flags:

Write your tests with parallelisation in mind.  Independent tests aren't enough, consider cross contamination (`system wide settings`) contaminating your tests at runtime.  For example if test A modifies
a system wide setting it can impact other tests, even tho they are not remotely reliant on each other.  Multi tenancy applications can really help with this, otherwise run a `@NotThreadSafe` run at the end of your run.
If you are running one test at a time, again I will find you and I will kill you.

---

### :crossed_flags: Pointless noise in page objects :crossed_flags:

Page objects should encapsulate user actions grouped together, not individual actions that interact on a per element basis.  Writing a `Login();` method is better than writing 3 methods to do the steps of logging in.

---

### :crossed_flags: Using field injection :crossed_flags:

Using field injection with any sort of DI mechanism, I will find you and I will kill you. Yes its easier, but it sucks.  Its gimmicky magic, decreases class testability, masks design errors with large classes.  When you inject into the field often you will 
not see beefy constructors that can prompt you to do some refactoring.

---

### Please contribute!

Now that we have that out of the way, I would also like that you create atleast 1 pull request to the selenide project when using this framework.  You can find the repository here:

https://github.com/codeborne/selenide

and ofcourse, open PR's here

# :triangular_flag_on_post: Framework stack

| Technology | Description | Link
| ------------- | ------------- | -------------
| **Java**  | Programming language)  | [Java](https://java.com/en/download/)
| **TestNG**  | Test framework for test ecosystem  | [TestNG](http://testng.org/doc/)
| **Selenium WebDriver**  | Browser manipulation  | [Selenium](https://www.seleniumhq.org/)
| **Rest Assured**  | Restful API DSL  | [Rest Assured](http://rest-assured.io/)
| **AssertJ**  | Powerful assertsions library  | [AssertJ](http://joel-costigliola.github.io/assertj/)
| **Maven**  | Build compilation, Dependency mgmt & test execution  | [Maven](https://maven.apache.org/)
| **JFaker** | Data Generator (when applicable) | [JFaker](https://github.com/sgianelli/JFaker)
| **Logback** | Logging framework | [Logback](https://logback.qos.ch/)
| **Bespoke Reporting** | Dashboard of test results and debug data | [Allure Reporting](https://github.com/allure-framework/allure2)
| **Guice** | Dependency injection | [Guice](https://github.com/google/guice)
| **Automation Assistant** | Framework assistance by me | [Automation Assistant](https://github.com/symonk/Automation-Assistant)
| **Selenium Grid** | Distributed testing | [Selenium Grid](https://www.seleniumhq.org/docs/07_selenium_grid.jsp)
| **Lombok** | Removal of boilerplate code | [Lombok](https://projectlombok.org/download)
| **Owner** | Properties management | [@Owner](http://owner.aeonbits.org/)
| **Selenide** | Selenium wrapper | [@Selenide](http://http://selenide.org)



### Contact me:

[![Linked In](https://img.shields.io/badge/Add%20Me%20On-LinkedIn-orange.svg)](https://www.linkedin.com/in/simonk09/)
[![Linked In](https://img.shields.io/badge/Join%20Me%20On-Slack-orange.svg)](https://testersio.slack.com)



