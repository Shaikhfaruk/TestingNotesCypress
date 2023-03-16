# Cypress Notes

### Install Cypress

```bash
npm install cypress --save-dev
```

### Run Cypress

```bash
npx cypress open
```

### Run Cypress in headless mode

```bash
npx cypress run
```

### Run Cypress headed mode

```bash
npx cypress run --headed
```

### Run Cypress in headless mode with a specific browser

```bash
npx cypress run --browser chrome
```

### Run Cypress in headless mode with a specific browser and record the test

```bash
npx cypress run --browser chrome --record
```

### Run Cypress in headless mode with a specific browser and record the test with a specific key

```bash
npx cypress run --browser chrome --record --key 12345678-1234-1234-1234-123456789012
```

## Cypress test

### Create a test

```bash
npx cypress open
```

### Create a test with a specific name

```bash
npx cypress open --spec "cypress/integration/mytest.spec.js"
```

### Create a test with a specific name and run it

```bash
npx cypress run --spec "cypress/integration/mytest.spec.js"
```

## Cypress Functions

### To launch application

```javascript
cy.visit("http://localhost:3000"); // whatever the URL is
```

### To get the title of the page

```javascript
cy.title();
```

### To get the URL of the page

```javascript
cy.url();
```

### Here is a Example

```javascript
describe("My First Test", () => {
  it("verify title-positive", () => {
    // lunch the app
    cy.visit("http://localhost:3000/");
    // check the title
    cy.title().should("eq", "Pitchspot");
  });

  it("verify title-negative", () => {
    // lunch the app
    cy.visit("http://localhost:3000/");
    // check the title
    cy.title().should("eq", "Pitchspot1");
  });
});
```

# Locators

### To get the element by ID

```javascript
cy.get("#id");
```

### To get the element by class

```javascript
cy.get(".class");
```

### To get the element by tag

```javascript
cy.get("tag");
```

### To get the element by attribute

```javascript
cy.get("[attribute]");
```

### To get the element by attribute and value

```javascript
cy.get("[attribute='value']");
```

### To get the element by attribute and value with wildcard

```javascript
cy.get("[attribute*='value']");
```

### To get the element by attribute and value with wildcard at the end

```javascript
cy.get("[attribute$='value']");
```

### To get the element by attribute and value with wildcard at the beginning

```javascript
cy.get("[attribute^='value']");
```

### To get the element by attribute and value with wildcard at the beginning and end

```javascript
cy.get("[attribute*='value']");
```

# Actions

### To click on the element

```javascript
cy.get("button").click();
```

### To type in the element

```javascript
cy.get("input").type("Faruk");
```

### To clear the element

```javascript
cy.get("input").clear();
```

### To select the element

```javascript
cy.get("select").select("Faruk");
```

### To check the element

```javascript
cy.get("input").check();
```

### To uncheck the element

```javascript
cy.get("input").uncheck();
```

# Assertions

### To check the title of the page

```javascript
cy.title().should("eq", "Pitchspot");
```

### To check the URL of the page

```javascript
cy.url().should("include", "http://localhost:3000");
```

### To check the element is visible

```javascript
cy.get("button").should("be.visible");
```

### To check the element is not visible

```javascript
cy.get("button").should("not.be.visible");
```

### To check the element is enabled

```javascript
cy.get("button").should("be.enabled");
```

### To check the element is disabled

```javascript
cy.get("button").should("be.disabled");
```

### To check the element is checked

```javascript
cy.get("input").should("be.checked");
```

### To check the element is not checked

```javascript
cy.get("input").should("not.be.checked");
```

### To check the element is selected

```javascript
cy.get("select").should("be.selected");
```

# Code Snippets

## To login

```javascript
describe("Login Test", () => {
  it("Login with valid credentials", () => {
    cy.visit("http://localhost:3000/login");
    cy.get('input[name="email"]').type("sfaruk1137@gmail.com");
    cy.get('input[name="password"]').type("Faruk123@");
    cy.get('button[type="submit"]').click();
    cy.url().should("include", "http://localhost:3000/dashboard");
  });
});
```

## To logout

```javascript
describe("Logout Test", () => {
  it("Logout", () => {
    // remove the cookie
    cy.clearCookie("token");
  });
});
```

## Before and After

```javascript
describe("My First Test", () => {
  before(() => {
    // runs once before all tests in the block
  });

  after(() => {
    // runs once after all tests in the block
  });

  beforeEach(() => {
    // runs before each test in the block
  });

  afterEach(() => {
    // runs after each test in the block
  });

  it("verify title-positive", () => {
    // lunch the app
    cy.visit("http://localhost:3000/");
    // check the title
    cy.title().should("eq", "Pitchspot");
  });

  it("verify title-negative", () => {
    // lunch the app
    cy.visit("http://localhost:3000/");
    // check the title
    cy.title().should("eq", "Pitchspot1");
  });
});
```

## Should vs Expect

```javascript
describe("My First Test", () => {
  it("verify title-positive", () => {
    // lunch the app
    cy.visit("http://localhost:3000/");
    // check the title
    cy.title().should("eq", "Pitchspot");
    cy.title().should("include", "Pitch");
    cy.title().should("not.eq", "Pitchspot1");
    cy.title().should("not.include", "Pitch1");
  });

  it("verify title-positive", () => {
    // lunch the app
    cy.visit("http://localhost:3000/");
    // check the title
    expect(cy.title()).to.eq("Pitchspot");
    expect(cy.title()).to.include("Pitch");
    expect(cy.title()).to.not.eq("Pitchspot1");
    expect(cy.title()).to.not.include("Pitch1");
  });
});
```

## Should all Methods

```javascript
describe("My First Test", () => {
  it("verify title-positive", () => {
    // lunch the app
    cy.visit("http://localhost:3000/");
    // check the title
    cy.title().should("eq", "Pitchspot");
    cy.title().should("include", "Pitch");
    cy.title().should("not.eq", "Pitchspot1");
    cy.title().should("not.include", "Pitch1");
  });
});
```

## Class prasent or not

```javascript
describe("My First Test", () => {
  it("verify title-positive", () => {
    // lunch the app
    cy.visit("http://localhost:3000/");
    // check the title
    cy.get("button").should("have.class", "btn");
    cy.get("button").should("not.have.class", "btn1");
  });
});
```

## ID prasent or not

```javascript
describe("My First Test", () => {
  it("verify title-positive", () => {
    // lunch the app
    cy.visit("http://localhost:3000/");
    // check the title
    cy.get("button").should("have.id", "btn");
    cy.get("button").should("not.have.id", "btn1");
  });
});
```

## Attribute prasent or not

```javascript
describe("My First Test", () => {
  it("verify title-positive", () => {
    // lunch the app
    cy.visit("http://localhost:3000/");
    // check the title
    cy.get("button").should("have.attr", "type", "submit");
    cy.get("button").should("not.have.attr", "type", "button");
  });
});
```

## Value prasent or not

```javascript
describe("My First Test", () => {
  it("verify title-positive", () => {
    // lunch the app
    cy.visit("http://localhost:3000/");
    // check the title
    cy.get("button").should("have.value", "Submit");
    cy.get("button").should("not.have.value", "Submit1");
  });
});
```

## Text prasent or not

```javascript
describe("My First Test", () => {
  it("verify title-positive", () => {
    // lunch the app
    cy.visit("http://localhost:3000/");
    // check the title
    cy.get("button").should("have.text", "Submit");
    cy.get("button").should("not.have.text", "Submit1");
  });
});
```

## To check color of the element

```javascript
describe("My First Test", () => {
  it("verify title-positive", () => {
    // lunch the app
    cy.visit("http://localhost:3000/");
    // check the title
    cy.get("button").should("have.css", "background-color", "rgb(0, 0, 255)");
    cy.get("button").should("not.have.css", "background-color", "rgb(0, 0, 0)");
  });
});
```
