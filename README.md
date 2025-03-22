
# Playwright Automation Testing with Page Object Model (POM) Framework

This project demonstrates end-to-end (E2E) testing of an e-commerce website using **Playwright** with **TypeScript** and **Page Object Model (POM)**. The objective is to automate the process of navigating between pages, sorting products, adding them to the cart, and completing the checkout process.


## Project Overview

This repository contains Playwright automation scripts written in TypeScript for an e-commerce website. The project follows the **Page Object Model** design pattern for better maintainability and readability of the test code.

## Project Structure

```
├── node_modules
├── pages/
│   ├── BasePage.ts
│   ├── CheckoutPage.ts
│   ├── CreateAccount.ts
│   ├── HomePage.ts
│   ├── ProductPage.ts
├── tests/
│   └── e2e.test.ts
└── Jenkinsfile
└── package-lock.json
└── package.json
└── playwright.config.ts
```
- **node_modules**: Contains installed npm packages and dependencies for the project.
- **pages**: Stores page object model classes for organizing test steps.
- **tests**: Contains the actual Playwright test scripts or test cases.
- **Jenkinsfile**: Defines the CI pipeline for Jenkins to run automated tests.
- **package-lock.json**: Locks the dependencies and their versions for consistent installs.
- **package.json**: Metadata about the project, including dependencies, scripts, and npm configuration.
- **playwright.config.ts**: Configuration file for Playwright defining browser settings, timeouts, and test options.

## Test Flow

The automated tests cover the following key actions on the e-commerce website:

1. **Homepage Navigation**:
   - Navigate to "Men", "Women", and "Gear" sections.
   - Verify that the correct page loads and contains the expected text.

2. **Product Sorting**:
   - Sort products by price and name.
   - Verify that the sorting options work as expected.

3. **Add Product to Cart**:
   - Navigate to a product page and add a product to the cart.
   - Handle selecting product options like size, color, and quantity.

4. **Checkout Process**:
   - Fill out shipping and billing details.
   - Select a payment method and place the order.
   - Verify success and confirmation messages after placing the order.

5. **Account Creation**:
   - After completing the checkout, create an account by entering user details.


# Playwright Automation Setup with Jenkins (Steps to Run This Repository Locally)

This guide helps you set up Playwright for automated testing with Jenkins integration.

## Steps

### 1. Download the Repository Locally
- Clone the repository to your local system:
  ```bash
  git clone https://github.com/your-username/your-repository.git
  cd your-repository
  ```

### 2. Install and Set Up Visual Studio
- Install [Visual Studio Code](https://code.visualstudio.com/) (or Visual Studio if you prefer).
- Open the folder containing your cloned repository from Visual Studio:
  - **File > Open Folder** and select your repository folder.

### 3. Initialize Playwright in the Project
- Open the terminal in Visual Studio Code and run the following command to install Playwright and its dependencies:
  ```bash
  npm init playwright@latest
  ```
  This will install Playwright and set up a configuration for your project.

  If you want to execute test cases in Playwright with a user interface, use the following command:

    ```bash
    npx playwright test --ui
    ```

### 4. Create and Push the Repository to GitHub
- Open Git and create a new repository (public or private).
- Get the Git clone URL form github (`https://github.com/your-username/your-repository.git`).

### 5. Set Up Git in the Project
- Initialize the Git repository:
  ```bash
  git init
  git add .
  git commit -m "Initial commit"
  git branch -M main
  git remote add origin https://github.com/your-username/your-repository.git
  git push -u origin main
  ```

### 6. Configure Jenkins for Running Playwright Tests

#### 6.1. Download Jenkins
- Go to [Jenkins Download](https://www.jenkins.io/download/) and download the latest version.
- Install and run Jenkins locally on your system.

#### 6.2. Access Jenkins
- Open Jenkins in your browser: [http://localhost:8080](http://localhost:8080).
- Log in and click **New Item** to create a new Jenkins project.
- Provide a name for your project, select **Freestyle project**, and click **OK**.

#### 6.3. Set Up Source Code Management in Jenkins
- In the project configuration, scroll to **Source Code Management**.
- Select **Git** and enter the **Repository URL** (use the URL of your repository).
- In **Branches to build**, enter `*/main` to build from the main branch.

#### 6.4. Configure Build Steps
- Add the following **Execute Windows batch command** build steps:

  1. Install Playwright and its dependencies:
     ```bash
     npm install --save-dev @playwright/test
     npx playwright install chromium
     ```

  2. Run Playwright tests:
     ```bash
     npx playwright test tests/e2e.test.ts --project=chromium --headed
     ```

#### 6.5. Save and Run the Build
- Click **Save** to save your Jenkins job.
- Click **Build Now** to trigger the build.
- Navigate to **Console Output** to check the test run results.

### 7. Verify Test Execution
- Ensure that the Playwright tests run and pass successfully in the Jenkins console output.

<img width="956" alt="image" src="https://github.com/user-attachments/assets/f7a07815-44a4-49b5-b26b-a83fc5a80351" />




