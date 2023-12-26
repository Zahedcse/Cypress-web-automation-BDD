# Cypress-web-automation-BDD
This is a cypress web automation project using BDD and POM

# Add-some-lines-to-the-project
Installing Cucumber
Step 1: To install Cucumber, run this command.

npm install --save-dev cypress-cucumber-preprocessor
Once installed, Cucumber devDependency in package.json can be seen below.

# Step 2: Add below code snippet in cypress.config.js

const { defineConfig } = require("cypress");
const cucumber = require("cypress-cucumber-preprocessor").default;
module.exports = defineConfig({
  e2e: {
    setupNodeEvents(on, config) {
      on("file:preprocessor", cucumber());
    },
  },
});


# Step 3: Add the below code snippet in package.json

"cypress-cucumber-preprocessor": {
    "nonGlobalStepDefinitions": false
  }

# Step 4: Add the below line in package.json
"step_definitions": "cypress/e2e/cucumber/Tests"

# Step 5: Add the below line in cypress.config.js to run .feature file only

specPattern: "**/*.feature",
