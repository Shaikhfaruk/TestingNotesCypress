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
