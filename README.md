# ParaBank Test Automation Framework (Playwright + TypeScript)

## 📖 Overview
[ParaBank](https://parabank.parasoft.com/) is a realistic online banking application that allows users to manage fund transactions.  
This project demonstrates an **End-to-End (E2E) Test Automation Framework** built using **Playwright with TypeScript**, covering **UI** and **API** test scenarios.  

The framework automates:
- User registration and login  
- Account creation and transaction flows  
- Fund transfer and bill payment  
- Validation of backend transactions via API  

---

## 🎯 Test Scenarios

### 🔹 UI Test Scenarios
1. Navigate to ParaBank application.  
2. Create a new user from the registration page (ensuring random and unique username on each execution).  
3. Login with the newly created user.  
4. Verify the global navigation menu on the homepage.  
5. Create a Savings account from “Open New Account” page and capture the account number.  
6. Validate that the Accounts Overview page displays correct balance details.  
7. Transfer funds from the newly created account to another account.  
8. Pay a bill using the account created in step 5.  
9. Assertions added at each validation step.  

### 🔹 API Test Scenarios
1. Search transactions using the **"Find Transactions"** API by amount for the bill payment done in UI step 8.  
2. Validate the JSON response details (transaction amount, accountId, etc.).  

---

## 🚀 Tech Stack
- **Playwright** – UI and API test automation  
- **TypeScript** – Strongly typed scripting language for better maintainability  
- **Node.js** – JavaScript runtime  
- **NPM** – Dependency and script management  

---

## ⚡ Playwright Features Utilized
This framework demonstrates various features of Playwright:

- **Browser Automation**  
  - Chromium browser for simulating UI interactions  
  - Page navigation, form filling, clicking elements  

- **Selectors**  
  - Locator strategies (`page.locator`, text, CSS, XPath) for reliable element handling  

- **Assertions**  
  - Built-in Playwright test assertions (`expect`) for validation of UI and API responses  

- **Fixtures and Hooks**  
  - `beforeAll` and `afterAll` hooks to set up and tear down API context  
  - Test isolation per scenario  

- **API Testing**  
  - Playwright’s `request.newContext()` to make direct REST API calls  
  - Assertion of HTTP response status codes and JSON payloads  

- **Random Data Generation**  
  - Randomized unique usernames in registration to avoid test data conflicts  

- **Parallel Execution**  
  - Playwright Test Runner executes scenarios in parallel for faster runs  

---

## 📂 Project Structure
├── tests
│ ├── ui
│ │ └── parabank-ui.spec.ts # UI Test Scenarios
│ ├── api
│ │ └── parabank-api.spec.ts # API Test Scenarios
├── utils
│ └── testDataHelper.ts # Helper to share data between UI & API tests
├── playwright.config.ts # Playwright configuration
├── package.json # Project dependencies & scripts
└── README.md # Project documentation


---

## 🛠️ Installation & Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/your-repo/parabank-playwright.git
   cd parabank-playwright
Install dependencies:


npm install
Run UI tests:


npx playwright test tests/ui/parabank-ui.spec.ts --headed
Run API tests:


npx playwright test tests/api/parabank-api.spec.ts
Run all tests:


npx playwright test
Generate test report:


npx playwright show-report
📊 Reporting
Playwright provides an HTML report after each run.

Execute npx playwright show-report to view results in the browser.

