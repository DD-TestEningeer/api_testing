# Restful-Booker API Automation Framework - Features and Use Cases

This framework is designed to automate API testing for the **Restful-Booker API** using **Java**, **RestAssured**, **TestNG**, **Log4j2**, and **ExtentReports**. The framework is modular, reusable, and provides logging and reporting capabilities. Below are the detailed features and use cases.

---

## Features

1. **API Endpoint Coverage**
   - Supports all major endpoints of Restful-Booker API:
     - **Auth**: Create authentication tokens.
     - **Booking**:
       - `GetBookingIds`: Fetch all booking IDs.
       - `GetBooking`: Fetch booking details by ID.
       - `CreateBooking`: Create a new booking.
       - `UpdateBooking`: Full update of a booking.
       - `PartialUpdateBooking`: Partial update of a booking.
       - `DeleteBooking`: Delete a booking by ID.

2. **Reusable Utility Methods**
   - `ApiUtils` class provides reusable methods for:
     - GET
     - POST
     - PUT
     - PATCH
     - DELETE
   - Each method logs request and response automatically.

3. **Configuration Management**
   - `config.properties` allows easy setup of:
     - Base URI
     - Retry counts
     - Other environment-specific settings

4. **Logging**
   - `LoggerHelper` integrates **Log4j2**.
   - Logs request details, response details, and test steps.
   - Stores logs in **logs/test.log** for debugging and auditing.

5. **Reporting**
   - Generates HTML reports using **ExtentReports**.
   - Reports include:
     - Test name
     - Status (Pass/Fail/Skip)
     - Logs
     - Stack trace for failures
     - Timestamp
   - Reports are saved in **reports/ExtentReport.html**.

6. **TestNG Integration**
   - Supports:
     - Parallel test execution
     - Test prioritization
     - Retry logic for failed tests
     - Custom listeners for reporting and logging

7. **Exception Handling**
   - Handles SSL errors, request failures, and invalid responses gracefully.
   - Provides meaningful logs for debugging.

8. **Thread-Safe Execution**
   - Uses `ThreadLocal` for ExtentReports to ensure thread-safe logging when running tests in parallel.

9. **Extensibility**
   - Easy to add new API endpoints or test scenarios.
   - Modular structure allows separation of:
     - Test logic (`tests/`)
     - Utilities (`utils/`)
     - Base setup (`base/`)
     - Listeners (`listeners/`)

---

## Use Cases

1. **Automated Regression Testing**
   - Run all API tests automatically to validate changes in the API.
   - Detect broken endpoints early.

2. **Smoke Testing**
   - Quickly validate critical endpoints like authentication and booking creation.

3. **Data Validation**
   - Verify correct response codes, payloads, and booking details.
   - Assert fields like `firstname`, `lastname`, `totalprice`, `bookingdates`.

4. **Performance Monitoring**
   - Log response times for each API request.
   - Identify slow-performing endpoints.

5. **Error Handling Verification**
   - Validate proper error codes for invalid requests, missing tokens, or unauthorized access.

6. **CI/CD Integration**
   - Easily integrate with Jenkins, GitHub Actions, or Azure Pipelines.
   - Automatically generate reports after each build or deployment.

7. **Test Documentation**
   - Reports provide detailed logs for auditing and documentation purposes.
   - Helps QA teams share results with developers or stakeholders.

8. **Parallel and Distributed Testing**
   - Supports parallel execution to save time.
   - Can be extended for distributed test execution in cloud-based environments.

---

## Benefits

- **Reduced Manual Effort**: Automates repetitive API validation tasks.
- **Improved Reliability**: Ensures consistent testing with reusable utilities.
- **Traceability**: Complete logs and reports allow tracing issues easily.
- **Scalability**: Add new endpoints or environments without changing the framework structure.
- **User-Friendly**: Clear reports and logs make it easy for testers and developers to understand results.

---

## Summary

This framework is ideal for **QA engineers** and **automation testers** who want to automate API testing for the Restful-Booker application.  
It provides **comprehensive coverage**, **reusable utilities**, **detailed logs**, and **rich HTML reports**, ensuring high-quality API testing and easy integration into CI/CD pipelines.
