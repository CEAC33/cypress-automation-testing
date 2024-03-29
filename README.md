# cypress-automation-testing

## Intro

https://www.cypress.io/

**What is Cypress?**

· Cypress is a next generation front end Automation testing tool built for the modern web applications

**How Cypress is Unique from other Automation tools?**

Cypress automatically waits for commands and assertions before moving on. No more async hell.

Ability to test Edge Testcases by Mocking the server response

Cypress takes snapshots as your tests run. We can hover over each commands in the Command Log to see exactly what happened at each step.

Because of its Architectural design, Cypress delivers fast, consistent and reliable test execution compared to other Automation tools

View videos of your entire tests execution when run from the Cypress Dashboard.

*******************************************************************************************

Cypress built on Node.js and comes packaged as an npm module,

As it is built on Node.js, It uses JavaScript for writing tests. But 90% of coding can be done using Cypress inbuilt commands which are easy to understand.

Cypress also bundles with jQuery and inherits many of jQuery methods for UI components Identification

**Cypress Architecture**

Most testing tools (like Selenium) operate by running outside of the browser and executing remote commands across the network. But Cypress engine directly operates inside the browser. In other words, It is the browser that is executing your test code

This enables Cypress to listen and modify the browser behavior at run time by manipulating DOM and altering Network requests and responses on the fly

Cypress open doors to New Kind of testing with Having ultimate control over your application (front and back)



Cypress Browser Support:


Chrome
Electron
Firefox & IE (Under Construction)


Cypress Components:

Test Runner
Dash Board Service



**Course Outcome:**

By end of this course, You should be able to Automate any Web App using Cypress
You will understand how Cypress is Unique to build Non Flaky Stable Automation tests with the help of jQuery
You can mock network requests and responses with Cypress
Ability to Design Cypress framework from scratch with all the Testing standards

Integrate Cypress Test Framework to Jenkins for CI/CD




**Course Prerequisites:**

None for 90% of lectures.
Basics of API knowledge when dealing with API mocking topics. (10% lectures)
JavaScript Basics are taught in parallel when required with Cypress concepts

## Cypress Installation & Project Setup

> Install NodeJS

```
brew install node
```

> Generate the package.json file

```
npm init
```

`package name:` automation

`version:` (default)

`description:` (default)

`entry point:` (default)

`test command:` (default)

`git repository:` (default)

`keywords:` (default)

`author:` ceac333

`license:` (default)

> Install Cypress - https://docs.cypress.io/guides/getting-started/installing-cypress.html#Installing

```
npm install cypress --save-dev
```

## Cypress Test Runner & Command Line Features

```
node_modules\.bin\cypress open
```

### Build Cypress Basic test and run from Test Runner

https://docs.cypress.io/guides/getting-started/writing-your-first-test.html

> Delete all files inside `cypress/integration/examples` folder

> Create a file `Test1.js` inside `cypress/integration/examples` folder

```js
describe('My First Test Suite', function() 
{
 
it('My FirstTest case', function() 
{

//test step

})

it('My Second case', function() 
{

//test step

})

})
```

Test1.js
```js
describe('My First Test Suite', function() 
{
 
it('My FirstTest case', function() 
{

cy.visit("https://www.bootcamps.online/")

})

})
```

Navigating to url - visit

### Running Cypress Tests in supported browsers

- Chrome
- Electron
- Canary
- Chromium

https://docs.cypress.io/guides/guides/command-line.html#Installation

Running all tests from the terminal:

```
./node_modules/.bin/cypress run
```

Running specific spec from the terminal:

```
npx cypress run --spec "cypress/integration/my-spec.js"
```

If you run Cypress from command line, Cypress runs in headless and in Electron browser 

Running all tests from the terminal opening the browser:

```
./node_modules/.bin/cypress run --headed
```

https://docs.cypress.io/guides/guides/launching-browsers.html

Running all tests from the terminal opening the browser in Chrome:

```
./node_modules/.bin/cypress run --headed --browser chrome
```

### Exploring the Cypress Project Framework Structure

- fixtures - this folder is responsible to store the test data
- integration - test cases and examples
- plugins - plugins are kind of listeners
- support - write your customized commands, reusable methods
- videos - videos of your tests
- node_modules - created when you install cypress
- cypress.json - configuration
- package.json - when you run npm install, it will look for the dependencies in this file

## Getting Started with Cypress Test Automation

### Cypress locator strategies and how to construct them

Cypress supports CSS Selectors only

- id - #idname - tagname#idname
- classname - .classname - tagname.classname
- attribute - tagname[attribute=value] 
- parent-child - form input

ChroPath Extension - https://chrome.google.com/webstore/detail/chropath/ljngjbnaijcbncmcnjfhigebomdlkcjo?hl=en

Inside Cypress Editor > Open Selector Playground

### Cypress inbuilt plugin in testRunner to generate locators

Intelligent Code Completion - https://docs.cypress.io/guides/tooling/intelligent-code-completion.html

```js
/// <reference types="Cypress" />

describe('My First Test Suite', function() 
{
 
it('My FirstTest case', function() 
{

cy.visit('https://rahulshettyacademy.com/seleniumPractise/#/')
cy.get('.search-keyword').type('ca')

})

})
```

### Basic Assertion in writing the tests with Cypress

https://docs.cypress.io/guides/references/assertions.html#Length

- id - #idname - tagname#idname
- classname - .classname - tagname.classname
- attribute - tagname[attribute=value] 
- parent-child - form input

ChroPath Extension - https://chrome.google.com/webstore/detail/chropath/ljngjbnaijcbncmcnjfhigebomdlkcjo?hl=en

Inside Cypress Editor > Open Selector Playground

### Cypress inbuilt plugin in testRunner to generate locators

Intelligent Code Completion - https://docs.cypress.io/guides/tooling/intelligent-code-completion.html

```js
/// <reference types="Cypress" />

describe('My First Test Suite', function() 
{
 
it('My FirstTest case', function() 
{

cy.visit('https://rahulshettyacademy.com/seleniumPractise/#/')
cy.get('.search-keyword').type('ca')
cy.wait(2000)
cy.get('.product').should('have.length',4)

})

})
```

### Handling Invisible elements with Cypress by understanding logs

### Cypress inbuilt plugin in testRunner to generate locators

Intelligent Code Completion - https://docs.cypress.io/guides/tooling/intelligent-code-completion.html

```js
/// <reference types="Cypress" />

describe('My First Test Suite', function() 
{
 
it('My FirstTest case', function() 
{

cy.visit('https://rahulshettyacademy.com/seleniumPractise/#/')
cy.get('.search-keyword').type('ca')
cy.wait(2000)
cy.get('.product:visible').should('have.length',4)

})

})
```

## Deep diving into Cypress Commands and its Asynchronous Nature

### Understanding get and find commands with Cypress

```js
/// <reference types="Cypress" />

describe('My First Test Suite', function() 
{
 
it('My FirstTest case', function() 
{

cy.visit('https://rahulshettyacademy.com/seleniumPractise/#/')
cy.get('.search-keyword').type('ca')
cy.wait(2000)
cy.get('.product').should('have.length',5)
cy.get('.product:visible').should('have.length',4)
//Parent child chaining
cy.get('.products').find('.product').should('have.length',4)
cy.get(':nth-child(3) > .product-action > button').click()
cy.get('.products').find('.product').eq(2).contains('ADD TO CART').click()

})

})
```

### Grabbing the text for validations using cypress text command

https://docs.cypress.io/api/commands/each.html#Syntax

```js
/// <reference types="Cypress" />

describe('My First Test Suite', function() 
{
 
it('My FirstTest case', function() 
{

cy.visit('https://rahulshettyacademy.com/seleniumPractise/#/')
cy.get('.search-keyword').type('ca')
cy.wait(2000)
cy.get('.product').should('have.length',5)
cy.get('.product:visible').should('have.length',4)
//Parent child chaining
cy.get('.products').find('.product').should('have.length',4)
cy.get(':nth-child(3) > .product-action > button').click()
cy.get('.products').find('.product').eq(2).contains('ADD TO CART').click()

cy.get('.products').find('.product').each(($el, index, $list) => {

const textVeg=$el.find('h4.product-name').text()

if(textVeg.includes('Cashews'))
{
$el.find('button').click()
}
})

})

})
```

### Cypress Asynchronous nature and its promise handling


```js
/// <reference types="Cypress" />

describe('My First Test Suite', function() 
{
 
it('My FirstTest case', function() 
{

cy.visit('https://rahulshettyacademy.com/seleniumPractise/#/')
cy.get('.search-keyword').type('ca')
cy.wait(2000)
cy.get('.product').should('have.length',5)
cy.get('.product:visible').should('have.length',4)
//Parent child chaining
cy.get('.products').find('.product').should('have.length',4)
cy.get(':nth-child(3) > .product-action > button').click()
cy.get('.products').find('.product').eq(2).contains('ADD TO CART').click()

cy.get('.products').find('.product').each(($el, index, $list) => {

const textVeg=$el.find('h4.product-name').text()

if(textVeg.includes('Cashews'))
{
$el.find('button').click()
}
})

})

})
```
