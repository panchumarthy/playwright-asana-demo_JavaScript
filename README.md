# Playwright Asana Demo — JavaScript

A data-driven end-to-end test suite built with [Playwright](https://playwright.dev/) for the [Asana-like Demo App](https://animated-gingersnap-8cf7f2.netlify.app/). All test scenarios are driven from a single centralized data file — adding a new scenario requires only a new data entry, not new test code.

---

## Project Structure

```
playwright-asana-demo_JavaScript/
├── data/
│   └── testData.js          # Centralized test data for all scenarios
├── pages/
│   ├── LoginPage.js         # Page Object — login/authentication
│   └── ProjectPage.js       # Page Object — board navigation & task inspection
├── tests/
│   └── board.spec.js        # Main test file (data-driven loop)
├── playwright.config.js     # Playwright configuration
└── package.json
```

---

## Test Cases

| ID    | Project            | Task                          | Column      | Tags                      |
|-------|--------------------|-------------------------------|-------------|---------------------------|
| TC-01 | Web Application    | Implement user authentication | To Do       | Feature, High Priority    |
| TC-02 | Web Application    | Fix navigation bug            | To Do       | Bug                       |
| TC-03 | Web Application    | Design system updates         | In Progress | Design                    |
| TC-04 | Mobile Application | Push notification system      | To Do       | Feature                   |
| TC-05 | Mobile Application | Offline mode                  | In Progress | Feature, High Priority    |
| TC-06 | Mobile Application | App icon design               | Done        | Design                    |

---

## Prerequisites

- [Node.js](https://nodejs.org/) v18 or higher
- npm

---

## Setup

```bash
# Install dependencies
npm install

# Install Playwright browsers
npx playwright install
```

---

## Running Tests

```bash
# Run all tests (headless)
npm test

# Run tests in headed mode (browser visible)
npm run test:headed

# Open the HTML test report
npm run report
```

---

## Design Patterns

- **Page Object Model (POM)** — `LoginPage` and `ProjectPage` encapsulate all selectors and actions, keeping tests clean and maintainable.
- **Data-driven testing** — All 6 test scenarios are declared in `data/testData.js`. The test loop in `board.spec.js` iterates over the dataset, so new scenarios require zero new test code.

---

## Configuration

Key settings in `playwright.config.js`:

| Setting             | Value                  |
|---------------------|------------------------|
| Browser             | Chromium (Desktop)     |
| Headless            | Yes                    |
| Retries             | 1                      |
| Screenshot          | On failure only        |
| Video               | Retained on failure    |
| Reporter            | HTML + List            |
