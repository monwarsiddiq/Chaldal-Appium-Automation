# Chaldal Appium Automation

## Introduction

**Chaldal-Appium-Automation** is a mobile UI test automation project built to automate testing of the **Chaldal** Android app — Chaldal being a popular online grocery and daily-essentials delivery platform in Bangladesh. The project uses **Appium** together with **Selenium WebDriver** and **TestNG** to drive the app on an Android device or emulator, allowing test cases to be written, organized, and executed the same way a Selenium-based web test suite would be, but targeting a native mobile application instead of a browser.

The repository is a standard **Maven** project, which makes it easy to manage dependencies, compile the code, and run the test suite from the command line or from any CI pipeline that supports Maven.

## Tech Stack

| Component | Technology |
|---|---|
| Language | Java 17 |
| Mobile Automation | Appium Java Client (`io.appium:java-client`, v9.3.0) |
| WebDriver | Selenium Java (v4.10.0) |
| Test Framework | TestNG (v7.10.2) |
| Build Tool | Maven |
| Logging | SLF4J Simple |

## Project Structure

```
Chaldal-Appium-Automation/
├── .mvn/                          # Maven wrapper files
├── .settings/                     # IDE (Eclipse) project settings
├── src/main/java/com/appium/      # Java source packages (test classes, drivers, etc.)
├── target/                        # Compiled build output
├── test-output/                   # TestNG execution reports
├── pom.xml                        # Maven project configuration and dependencies
├── testng.xml                     # TestNG suite definition
└── .classpath / .project          # Eclipse project metadata
```

The test suite is configured through `testng.xml`, which currently points to the `com.appium.test.AndroidAppTest` class as the entry point for running the automated Android test scenarios.

## Purpose

This project serves as an example/practice framework for **mobile test automation**, demonstrating how to:

- Configure Appium desired capabilities to launch and interact with an Android app
- Structure a Java + Maven + TestNG project for mobile automation
- Write and execute UI test cases against a real-world e-commerce style application (Chaldal)

## Prerequisites

To run the tests in this repository, you will typically need:

- Java Development Kit (JDK) 17
- Apache Maven
- Node.js and the Appium server installed globally (`npm install -g appium`)
- Android SDK / Android Studio with an emulator, or a physical Android device with USB debugging enabled
- The Chaldal Android APK installed (or available) on the target device/emulator

## Running the Tests

Once Appium server is running and a device/emulator is connected, the test suite can be executed via Maven, for example:

```bash
mvn test
```

TestNG will pick up the suite defined in `testng.xml` and execute the `AndroidAppTest` class. Test execution results and reports are generated in the `test-output/` directory.

## Notes

- The project does not currently include a detailed setup guide, so capability configuration (device name, platform version, app path, etc.) should be reviewed directly in the source code under `src/main/java/com/appium/` before running the tests.
- Contributions, improvements, and additional test coverage are welcome.
