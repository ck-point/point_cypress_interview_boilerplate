# Point E2E Test Shell

This repository contains a minimal setup to help you get up and running with writing Cypress end-to-end test cases for Point's `Know Before You Go` product.

We have provided the baseline functionality to load the site and login to the application. You can then build upon this to create additional test scenarios.

# Know Before You Go (KBYG)

`Know Before You Go` enables Point's partners to get a preliminary estimate on residential properties to see if they might be eligible for our [HEI product](https://point.com/hei).

The system under test is located at: https://partner-qa.point.dev

The application workflow is as follows:

1. Log into the application by providing an email address.
1. Input a complete property address or choose one of the suggested auto-completed addresses, then click `Search`.
1. Confirm or edit the the property address on the following page to continue.
   - In the case of a multi-unit address (e.g. a condominium complex), the user will need to specify the exact unit.
1. The final page will indicate if the property appears to be eligible for an HEI investment, and if so, how large the investment could be.
   - The user may then edit some attributes about the property's value or mortgage balance to get a more accurate estimate as necessary.

# Getting Started

### This project is using the following packages:

- [Cypress 12.x](https://www.npmjs.com/package/cypress)
- [Cypress Testing Library](https://testing-library.com/docs/cypress-testing-library/intro/)
  - Using these Testing Library style selectors is our preferred way of interacting with DOM elements, so these commands have been [pre-installed](https://github.com/ck-point/point_cypress_interview_boilerplate/blob/main/cypress/support/commands.js#L26) in the `/support` directory. You are encouraged to use them, but it's not required if you are more comfortable with the native Cypress selectors.

### Installation and running tests:

**Pre-requisites:** You will need `git` and `yarn` installed in your working environment.
_(To install `yarn`: https://classic.yarnpkg.com/en/docs/install)_

1. Use `git` to clone this repository to your environment
1. Run `yarn install` to download and install Cypress
1. Run `yarn test` to open the Cypress interactive test runner
1. When the test client opens, choose the `E2E Testing` options and select a browser to test in
1. From there, you will see the `start_here` [spec file](https://github.com/ck-point/point_cypress_interview_boilerplate/blob/main/cypress/e2e/start_here.cy.js). This file contains a single test which will login to KBYG and leave the user on the `/search` page.
   - Note that this test uses a custom command `kbygLogin()` which is available to use in your tests as well. It can be found in the [commands.js](https://github.com/ck-point/point_cypress_interview_boilerplate/blob/main/cypress/support/commands.js) file.
