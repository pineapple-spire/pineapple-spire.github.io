# Pineapple-Spire

[![pineapple-spire-ci](https://github.com/pineapple-spire/pineapple-spire/actions/workflows/ci.yml/badge.svg)](https://github.com/pineapple-spire/pineapple-spire/actions/workflows/ci.yml)

## Table of Contents

- [Overview](#overview)
- [Deployment](#deployment)
- [User Guide](#user-guide)
  - [Landing Page](#landing-page)
  - [Index Pages](#index-pages)
  - [Sign In and Sign Up](#sign-in-and-sign-up)
  - [Home Page](#home-page)
  - [Financial Compilation Page](#fc-page)
- [Community Feedback](#community-feedback)
- [Developer Guide](#developer-guide)
  - [Quality Assurance](#quality-assurance)
- [Development History](#development-history)
- [Continuous Integration](#continuous-integration)
- [Walkthrough Videos](#walkthrough-videos)
- [Example Enhancements](#example-enhancements)
- [Team](#team)
- [Team Contract](#team-contract)

---

## Overview

Pineapple-Spire is designed to create an optimized **Financial Sustainability Model**, integrating it into a web-based platform with a user-friendly interface.

---

## Deployment

(Details about deployment will go here.)

---

## User Guide

This section provides a walkthrough of the Pineapple-Spire user interface and its capabilities.

### Landing Page

The landing page is presented to users when they visit the site's top-level URL. This page allows users to navigate the specific financial analysis tooling the application covers.

### Index Pages

(Details about index pages.)

### Sign In and Sign Up

(Details about the sign-in and sign-up process.)

### Home Page

(Details about the home page features.)

### Financial Compilation Page

The financial compilation page features a 12 year forecast output of various financial information. Users are able to calculate their 12 year forecast by choosing if they want to view their data using the average of the past three years information or use a percent multiplier from 0-100%.

---

## Community Feedback

(Information about community feedback and how it is incorporated into development.)

---

## Developer Guide

### Quality Assurance

(Quality assurance processes and standards.)

---

## Development History

The development process for Pineapple-Spire adheres to [Issue Driven Project Management](https://courses.ics.hawaii.edu/ics414s25/modules/project-management/) practices. In summary:

- Development is organized into **Milestones**.
- Each milestone consists of a set of tasks.
- Tasks are described using GitHub Issues and assigned to individual developers.
- Tasks typically involve work that can be completed in **2-4 days**.
- Each task is developed in a separate Git branch named `issue-XX`, where `XX` is the issue number.
- Once a task is complete, its corresponding issue is closed, and the branch is merged into `master`.
- Task statuses (To Do, In Progress, Complete) are managed via a GitHub Project Board.

<details>
  <summary><strong>Milestone 1</strong></summary>

[Milestone 1 Project Board](https://github.com/orgs/pineapple-spire/projects/1)

#### Landing Page
<img src="images/Spire Homepage.png" alt="Landing Page" width=600px>

#### Sign In Page
<img src="images/Sign-In-Page.png" alt="Sign In Page" width=600px>

#### Sign Up Page
<img src="images/Sign-Up-Page.png" alt="Sign Up Page" width=600px>

#### Financial Compilation Pages

##### Income Statement Page
<img src="images/fc-income-statement-page.png" alt="Financial Compilation Income Statement Page" width=600px>

##### Costs of Goods Page
<img src="images/fc-costs-of-goods-page.png" alt="Financial Compilation Costs of Goods Page" width=600px>

##### Operating Expenses Page
<img src="images/fc-operating-expenses-page.png" alt="Financial Compilation Operating Expenses Page" width=600px>

##### Assets Page
<img src="images/fc-assets-page.png" alt="Financial Compilation Assets Page" width=600px>

##### Liabilities and Equity Page
<img src="images/fc-liabilities-equity-page.png" alt="Financial Compilation Liabilities and Equity Page" width=600px>

#### Sustainability Model Page
<img src="images/sustainability-model.png" alt="Sustainability Model Page" width=600px>

#### Auditor Page
<img src="images/Auditor%20Role%20Page%20Mockup.png" alt="Auditor Page" width=600px>

#### Stress Test Tool Page
<img src="images/Stress Test Tool Page.png" alt="Stress Test Tool" width=600px>

#### Stress Test 1 Page
<img src="images/stress-test-1.png" alt="Stress Test 1" width=600px>

#### Stress Test 2 Page
<img src="images/stress-test-2.png" alt="Stress Test 2" width=600px>

#### Stress Test 3 Page
<img src="images/stress-test-3.png" alt="Stress Test 3" width=600px>

#### Stress Test 4 Page
<img src="images/stress-test-4.png" alt="Stress Test 4" width=600px>

#### Stress Test 5 Page
<img src="images/stress-test-5.png" alt="Stress Test 5" width=600px>

</details>

<details>
  <summary><strong>Milestone 2</strong></summary>

[Milestone 2 Project Board](https://github.com/orgs/pineapple-spire/projects/2)

#### Landing Page
<img src="images/M2/Landing.png" alt="Landing Page" width=600px>

#### Sign In Page
<img src="images/M2/Signin.png" alt="Sign In Page" width=600px>

#### Sign Up Page
<img src="images/M2/Signup.png" alt="Sign Up Page" width=600px>

#### About Page
<img src="images/M2/About.png" alt="About Page" width=600px>

#### Financial Compilation Page
<img src="images/M2/FC.png" alt="Financial Compilation Page" width=600px>

#### Fiscal Sustainability Model Page
<img src="images/M2/FSM.png" alt="Fiscal Sustainability Model Page" width=600px>

#### Stress Test Tool Page
<img src="images/M2/Stress.png" alt="Stress Test Tool Page" width=600px>

</details>

<details>
  <summary><strong>Milestone 3</strong></summary>

[Milestone 3 Project Board](https://github.com/orgs/pineapple-spire/projects/3)

</details>

---

## Continuous Integration

Our project leverages GitHub Actions to automate our continuous integration (CI) process. The pipeline is triggered on pushes and pull requests to our primary branche (`main`), ensuring that every change is tested.

### How It Works

1. **Triggering the Pipeline:**  
   The workflow initiates on code pushes and pull requests, ensuring that all updates are validated.

2. **Environment Setup:**  
   - **Checkout Code:** The latest version of the repository is checked out.
   - **Node Environment:** The pipeline sets up Node.js using the latest LTS version.
   - **Dependency Installation:** Dependencies are installed using `npm ci` for a clean and reproducible environment.

3. **Testing and Linting:**  
   - **Playwright Setup:** Required browsers are installed via Playwright for acceptance testing.
   - **ESLint:** Code quality is enforced by running ESLint to catch potential static issues early.
   - **End-to-End Tests:** Playwright tests are executed to validate the application's behavior.

4. **Artifact Upload:**  
   The Playwright test report is uploaded as an artifact (retained for 30 days) to assist in debugging and continuous improvement.

5. **Deployment:**  
   Once all tests pass, the updated application is deployed to Vercel, which leverages a serverless PostgreSQL database for high availability and efficient performance.

### CI Pipeline Configuration

```yaml
name: ci-pineapple-spire
on:
  push:
    branches: [main, master]
  pull_request:
    branches: [main, master]
jobs:
  test:
    timeout-minutes: 60
    runs-on: ubuntu-latest
    environment: Production
    env:
      POSTGRES_PRISMA_URL: ${{ vars.POSTGRES_PRISMA_URL }}
      POSTGRES_URL_NON_POOLING: ${{ vars.POSTGRES_URL_NON_POOLING }}
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: lts/*
      - name: Install dependencies
        run: npm ci
      - name: Install Playwright Browsers
        run: npx playwright install --with-deps
      - name: Run ESLint
        run: npm run lint
      - name: Run Playwright Tests
        run: npx playwright test
      - uses: actions/upload-artifact@v4
        if: always()
        with:
          name: playwright-report
          path: playwright-report/
          retention-days: 30
```

---

## Walkthrough Videos

(Links and descriptions of walkthrough videos showcasing the project.)

---

## Example Enhancements

(Examples of potential enhancements or feature improvements.)

---

## Milestones

<ul>
  <li><a href="https://github.com/orgs/pineapple-spire/projects/1">Milestone 1</a></li>
  <li><a href="https://github.com/orgs/pineapple-spire/projects/2">Milestone 2</a></li>
  <li><a href="https://github.com/orgs/pineapple-spire/projects/3">Milestone 3</a></li>
</ul>

## Team

The project was designed, implemented, and maintained by:

- [Adriel White](https://adrielwhite.github.io/)
- [Kye Steele](https://kyesteele.github.io/)
- [Keiko Raiola](https://keikotr.github.io/)
- [Jake Dickinson](https://jaked332.github.io/)
- [Eden Parungao](https://edenkp.github.io/)
- [Shane Baclig](https://uhm-shaneb.github.io/)
- [Zachary Stoddard](https://hcazzz.github.io/)

---

## Team Contract

View our team contract here: [Pineapple-Spire Team Contract](https://docs.google.com/document/d/1FcM9N-iCkzPbdlifyuLXAwvtmEhThMv8Lw95GmEuUC8/edit?usp=sharing).
