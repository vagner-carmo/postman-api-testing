# Postman API Testing

API testing automation project using Postman and Newman, focused on validating REST API behavior, response data, authentication, and business rules.

This repository is part of my Software QA portfolio and demonstrates practical skills in API testing, test scripting, test data management, and command-line test execution.

## 🎯 Project Objectives

- Validate REST API endpoints and HTTP response status codes.
- Verify response headers, messages, and JSON response structures.
- Cover positive and negative test scenarios.
- Validate API responses against JSON Schemas.
- Use dynamic test data to reduce dependencies on fixed values.
- Manage authentication tokens and environment variables.
- Execute automated API tests through Newman.
- Generate HTML test reports for result analysis.

## 🛠️ Technologies and Tools

- **Postman:** API requests, collections, environment variables, and automated test scripts.
- **Newman:** Command-line execution of Postman collections.
- **JavaScript:** Automated assertions and test scripting.
- **JSON Schema:** Response structure validation.
- **newman-reporter-htmlextra:** HTML test report generation.
- **Node.js and npm:** Dependency management and test execution.
- **Git and GitHub:** Version control and project hosting.

## 🧪 Test Coverage

The project uses the [ServeRest API](https://serverest.dev/) to exercise authentication and resource management endpoints.

### Authentication and Login

- Successful login with valid credentials.
- Login with invalid credentials.
- Login with empty fields.
- Authentication response and authorization token validation.

### User Management

- Successful user creation.
- Creation using an existing email.
- Creation with empty or invalid fields.
- Retrieval of all users.
- Retrieval of a user by ID.
- Retrieval using a nonexistent ID.
- Successful user update.
- Update using an existing email.
- Update with an invalid or empty ID.
- Successful user deletion.
- Validation that a deleted user can no longer be retrieved.
- Deletion using a nonexistent ID.

### Product Management

- Successful product creation.
- Creation using an existing product name.
- Creation with empty fields.
- Retrieval of all products.
- Retrieval of a product by ID.
- Retrieval using a nonexistent ID.
- Successful product update.
- Update using an existing product name.
- Update with an invalid or empty ID.
- Successful product deletion.
- Validation that a deleted product can no longer be retrieved.
- Deletion using a nonexistent ID.
- Authentication and authorization validation for protected operations.

## ✅ Automated Validations

The collection includes reusable validation patterns to verify:

- HTTP status codes.
- Response content type.
- Expected response messages.
- Required response properties.
- Data types and field values.
- JSON Schema compliance.
- Generated resource IDs.
- Consistency between API responses and environment variables.
- Authentication and authorization behavior.
- Resource state after create, update, and delete operations.

## 🔄 Test Data and Authentication

The collection uses dynamic values to minimize dependencies on predefined test data.

- Postman dynamic variables generate values such as random names, email addresses, passwords, and timestamps.
- Setup requests create users and products required by subsequent scenarios.
- Environment variables store generated resource IDs and test data.
- Authentication tokens are captured from successful login responses and reused in protected requests.
- Follow-up requests validate that created or updated resources contain the expected data.

This approach improves test repeatability and reduces conflicts caused by previously registered data.

## 📁 Project Structure

```text
postman-api-testing/
├── collections/
│   └── ServeRest.postman_collection.json
├── environments/
│   └── ServeRestEnvironment.postman_environment.json
├── reports/
│   └── .gitkeep
├── .gitignore
├── package.json
├── package-lock.json
└── README.md
```

| File or folder | Description |
|---|---|
| `collections/` | Exported Postman collection containing API requests and automated assertions. |
| `environments/` | Environment configuration and variables used during execution. |
| `reports/` | Destination for generated HTML test reports. |
| `.gitignore` | Excludes dependencies and generated reports from version control. |
| `package.json` | Defines project dependencies and the test execution script. |
| `package-lock.json` | Locks dependency versions for reproducible installations. |

## ⚙️ Prerequisites

Before running the project, install:

- [Node.js](https://nodejs.org/)
- [Git](https://git-scm.com/)
- [Postman](https://www.postman.com/downloads/) (optional for command-line execution; recommended for exploring and editing the collection)

Newman and the HTML reporter are installed as local project dependencies through npm.

## 🚀 Installation

Clone the repository:

```bash
git clone https://github.com/vagner-carmo/postman-api-testing.git
```

Navigate to the project directory:

```bash
cd postman-api-testing
```

Install the dependencies defined in the lockfile:

```bash
npm ci
```

## ▶️ Running the Tests

Execute the complete collection using the configured npm script:

```bash
npm run test:api
```

This command:

1. Runs the exported Postman collection with Newman.
2. Loads the configured environment.
3. Executes the automated assertions.
4. Displays the execution results in the terminal.
5. Generates an HTML report.

The HTML report is saved to:

```text
reports/report.html
```

Open the generated file in a browser to inspect the test results and execution details.

The `reports/report.html` file is generated locally and excluded from version control. The `reports/.gitkeep` file ensures the directory remains available after cloning the repository.

## 📊 Test Reports

The project uses `newman-reporter-htmlextra` to generate an HTML report.

The report helps visualize request execution, test results, and failures, making it easier to review the collection run beyond the terminal output.

Reports are regenerated on subsequent executions and are not committed to the repository by default.

## 🔐 Security Considerations

- Do not commit real passwords, access tokens, or other sensitive credentials.
- Use appropriate environment variables for configuration.
- Review exported Postman environments before publishing them.
- Avoid including sensitive response data in public reports.

## 📚 References

- [Postman Documentation](https://learning.postman.com/)
- [Newman Documentation](https://learning.postman.com/docs/reference/newman-cli/installing-running-newman/)
- [Newman HTML Extra Reporter](https://www.npmjs.com/package/newman-reporter-htmlextra)
- [ServeRest API](https://serverest.dev/)

## 👨‍💻 Author

**Vagner Carmo**  
Software QA Analyst | CTFL Certified

## 📫 Contact

- 💼 LinkedIn: [Vagner Carmo](https://www.linkedin.com/in/vagner-do-carmo/)
- 💻 GitHub: [vagner-carmo](https://github.com/vagner-carmo)
