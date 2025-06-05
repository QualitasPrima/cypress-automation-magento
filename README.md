# Cypress E2E Test Automation for Magento Luma Demo

This project contains an End-to-End (E2E) test automation suite for the Magento Luma demo e-commerce website ([https://magento.softwaretestingboard.com/](https://magento.softwaretestingboard.com/)). It is built using Cypress with TypeScript and is designed to demonstrate best practices in test automation, including the Page Object Model (POM).

## 🌟 Purpose

This project serves as a portfolio piece to showcase skills and understanding in:
- Modern E2E test automation using Cypress and TypeScript.
- Implementing the Page Object Model (POM) for creating maintainable, scalable, and readable test suites.
- Writing clear, concise, and effective automated test scripts covering critical user flows.
- Test configuration, execution, and (eventually) reporting.
- Best practices in test automation project structure and version control with Git/GitHub.

## 🛠️ Tech Stack

- **Automation Framework:** [Cypress](https://www.cypress.io/) (Version X.Y.Z - *You will update this with the actual version once Cypress is installed*)
- **Language:** [TypeScript](https://www.typescriptlang.org/)
- **Core Test Runner & Assertion Library:** Cypress built-in
- **IDE:** [Visual Studio Code](https://code.visualstudio.com/)
- **Package Manager:** [npm](https://www.npmjs.com/) (or Yarn - *Specify which one you decide to use during setup*)
- **Version Control:** Git & GitHub

## 🚀 Features Covered

This automation suite aims to cover the following key features and user flows of the Magento Luma application:

*(This section will be populated with specific test suites/features as they are developed. Examples below)*
- **User Account Management:**
    - Successful User Registration
    - User Login with Valid Credentials
    - User Login with Invalid Credentials
    - User Logout
- **Product Discovery:**
    - Search for Products by Name/Keyword
    - Navigate to Product Categories
    - Basic Filtering and Sorting on PLP
- **Product Detail Page (PDP):**
    - Select Product Options (e.g., Size, Color)
    - Update Product Quantity
    - Add Product to Cart
- **Shopping Cart:**
    - Verify Cart Contents
    - Update Item Quantity in Cart
    - Remove Item from Cart
    - Apply Valid Discount Code
- **Checkout Process:**
    - E2E Guest User Checkout
    - E2E Registered User Checkout

## 🚦 Getting Started (Local Setup)

Follow these instructions to set up the project locally and run the tests.

### Prerequisites

Ensure you have the following installed on your system:
- **Node.js:** Version 18.x or later recommended (Check with `node -v`). You can download it from [nodejs.org](https://nodejs.org/).
- **npm:** (Usually comes with Node.js - Check with `npm -v`)

### Installation & Setup

1.  **Clone the repository:**
 
    git clone [https://github.com/](https://github.com/)[QualitasPrima]/cypress-automation-magento.git

2.  **Navigate to the project directory:**
  
    cd cypress-automation-magento


3.  **Install project dependencies:**
4.  
    Using npm:

    npm install

    This command will download Cypress and all other necessary packages defined in `package.json` (once we create `package.json` in the local setup steps).

5.  **(Optional) Environment Configuration:**
    *(If environment-specific configurations are used, e.g., via `.env` files or `cypress.config.ts`, instructions will be provided here. For now, we will likely use the base URL in `cypress.config.ts`.)*

## ධ Running Tests

Cypress tests can be run in two main modes:

### 1. Cypress Test Runner (Interactive Mode)

This mode opens the Cypress application, allowing you to see tests run in real-time, debug, and view command logs. This is recommended for writing and debugging tests.

To open the Test Runner:

Using npm:

npx cypress open

### 2. Headless Mode (Command Line Interface - CLI)
This mode runs tests in the background without launching a browser UI. It's ideal for running tests in CI/CD pipelines or for full regression runs. Screenshots and videos are typically recorded automatically for failing tests in this mode.

To run all tests headlessly:

Using npm:

npx cypress run

To run tests from a specific spec file headlessly:

Using npm:

npx cypress run --spec "cypress/e2e/path/to/your/specfile.cy.ts"

## 📂 Project Structure
The project follows a standard Cypress structure, with key customizations for organization and maintainability:

```
cypress-automation-magento/
├── cypress/
│   ├── e2e/                     # Contains all test spec files (e.g., *.cy.ts)
│   │   └── (Sub-folders for feature groups like 'user-management', 'checkout', etc.)
│   ├── fixtures/                # Test data (e.g., userCredentials.json)
│   ├── pageObjects/             # Page Object Model (POM) classes (e.g., LoginPage.ts, HomePage.ts)
│   ├── support/                 # Reusable custom commands, utility functions
│   │   ├── commands.ts          # Custom Cypress commands
│   │   └── e2e.ts               # Imports commands.ts, global configurations
│   └── downloads/               # Files downloaded during tests (usually gitignored)
│   └── screenshots/             # Screenshots taken on test failure (usually gitignored)
│   └── videos/                  # Videos recorded during headless runs (usually gitignored)
├── node_modules/                # Project dependencies (gitignored)
├── .gitignore                   # Specifies intentionally untracked files that Git should ignore
├── cypress.config.ts            # Cypress configuration file (baseUrl, viewport settings, etc.)
├── package.json                 # Lists project dependencies and scripts
├── package-lock.json (or yarn.lock) # Records exact versions of dependencies
├── README.md                    # This file: project overview and instructions
└── tsconfig.json                # TypeScript compiler options
```

## 🏛️ Page Object Model (POM)
This project utilizes the Page Object Model (POM) design pattern to enhance test maintenance and reduce code duplication.

Each page or significant component of the application under test (AUT) is represented by a corresponding class (e.g., HomePage.ts, LoginPage.ts, ProductPage.ts).
These classes encapsulate the elements (locators) and the methods (user interactions/operations) specific to that page/component.
Test scripts then use these Page Object methods to interact with the application, making the tests cleaner, more readable, and easier to update if the UI changes.
Page objects are typically stored in the cypress/pageObjects/ directory.

## 📊 Reporting
Screenshots & Videos: Cypress automatically captures screenshots on test failure and records videos of test runs in headless mode. These are stored in cypress/screenshots/ and cypress/videos/ respectively (though typically gitignored, examples might be referenced for portfolio purposes if a failure is being discussed).

## ✨ Best Practices Demonstrated

This project aims to demonstrate several test automation best practices:
- **Clear Naming Conventions:** For test files, suites, test cases, and POM elements.
- **Modularity & Reusability:** Through POM and custom commands.
- **Readability:** Well-structured tests and comments where necessary.
- **Maintainability:** Designing tests to be resilient to minor UI changes (via POM).
- **Data Management:** Using fixtures for test data where appropriate.
- **Explicit Waits (Avoidance):** Leveraging Cypress's built-in retry-ability and avoiding unnecessary explicit waits.
- **Configuration Management:** Using `cypress.config.ts` for global settings.
- **TypeScript for Type Safety:** Reducing errors and improving code quality..
