# **E-commerce Automation Framework**

## **Project Overview**
This is a Maven-based automation framework built using **TestNG** for testing an eCommerce web application. The framework automates end-to-end test cases, from user registration and product purchase to order history verification. The design follows the **Page Object Model (POM)** pattern, promoting maintainability and code reusability.

## **Features**
- **Maven Structured Framework**: Organized as a Maven project with appropriate dependencies.
- **Page Object Model (POM)**: Ensures the separation of locators and actions from test scripts.
- **Parallel Execution**: Supported using thread-safe mechanisms, enabling faster test runs.
- **Data-Driven Testing**: Integrated with HashMap, and TestNG’s `DataProvider` for parameterization.
- **TestNG Listeners**: Automatically captures screenshots on test failures and logs test execution.
- **Retry Mechanism**: Reruns flaky tests, reducing false negatives.
- **HTML Reports**: Generates detailed **Extent Reports** for easy analysis of test results.
- **Jenkins Integration**: Seamlessly integrates with Jenkins for CI/CD, with support for parameterized builds and scheduled test runs.

## **Technologies Used**
- **Java**
- **Selenium WebDriver**
- **TestNG**
- **Maven**
- **Extent Reports**
- **Jenkins**

## **Project Structure**
```
ecommerce-automation-framework
ecommerce-automation-framework
├── src
│   ├── main
│   │   ├── java
│   │   │   ├── abstractComponents       # Contains reusable components
│   │   │   │   ├── BasePage.java        # Contains explicit waits and common methods
│   │   │   ├── pages                    # Contains Page Object classes for eCommerce website
│   │   │   ├── resources                # Extent report(initialization), global property(browser) classes
│   ├── test
│   │   ├── java
│   │   │   ├── tests                    # Test classes for various scenarios
│   │   ├── Test components              # Base test, listeners
├── test-output                          # Stores Extent Reports and other test results
├── pom.xml                              # Maven configuration file with dependencies
├── README.md                            # Project documentation

```

## **Setup Instructions**
### **Prerequisites**
- Java 8 or higher
- Maven
- ChromeDriver or any other browser driver installed
- A preferred IDE (e.g., IntelliJ IDEA, Eclipse)

### **Installation Steps**
1. **Clone the repository**:
   ```bash
   git clone https://github.com/Sankr20/Ecommerce-Site-Automation-Framework.git
   cd Ecommerce-Site-Automation-Framework
   ```
2. **Install dependencies**:
   Run the following command to install all required dependencies:
   ```bash
   mvn clean install
   ```

3. **Configure Browser and Global Properties**:
   In the `BaseTest.java` file, configure the browser and global properties like URLs and timeouts as per your environment.

## **Running Tests**
### **Using Maven**
You can run all tests with Maven using the following command:
```bash
mvn clean test
```

### **Using TestNG.xml**
You can execute tests by directly running the `testng.xml` file, which categorizes and groups the test cases for better execution management:
```bash
<project-root>/src/test/resources/testng.xml
```

### **Parallel Execution**
To run tests in parallel:
1. Set `parallel` to `tests` or `methods` in `testng.xml`:
   ```xml
   <suite name="Automation Suite" parallel="tests" thread-count="2">
   ```
2. Run the following Maven command:
   ```bash
   mvn clean test -DsuiteXmlFile=testng.xml
   ```

## **Test Reports**
After executing tests, you can find the **Extent HTML Reports** in the `test-output/` folder. Open the `index.html` file to view the detailed report:
```bash
test-output/ExtentReports/index.html
```

## **Jenkins Integration**
The project is integrated with Jenkins for Continuous Integration (CI). Use the following steps to set up Jenkins:
1. Add a new Maven job in Jenkins.
2. Set up the GitHub repository link for the job.
3. Use the following Maven command in the Jenkins job:
   ```bash
   mvn clean test
   ```
4. Optionally, add a **Jenkinsfile** to automate the CI process with parameterized builds and scheduled jobs.

## **Contributing**
If you'd like to contribute to this project, feel free to fork the repository and submit a pull request. Contributions are always welcome!

### **Contribution Guidelines**:
- Fork the repository.
- Create a feature branch (`git checkout -b feature-branch`).
- Make your changes.
- Commit the changes (`git commit -m 'Added feature'`).
- Push to the branch (`git push origin feature-branch`).
- Create a new pull request.
