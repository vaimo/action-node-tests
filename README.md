# GitHub Action for Node.js Tests

This action is used to execute tests in Node.js projects.

**Author:** Patryk Walus (patryk.walus@vaimo.com)

## Supported Versions

- **v2**
    - Added configurable package manager support (npm, yarn, pnpm).
    - `package-manager` input is now required.
    - Upgraded `dorny/test-reporter` from v2 to v3.
    - Pinned `MishaKav/jest-coverage-comment` to v1 (was @main).
- **v1**
    - Test execution action for Node.js projects (yarn only).

## Usage

```yaml
- name: Run Tests
  uses: vaimo/action-node-tests@v2
  with:
    # Package manager to use. Supported values: npm, yarn, pnpm. (Required)
    package-manager: yarn

    # Directories where JUnit report files are located (Optional)
    # If not specified, defaults to */junit.xml
    junit-test-report-path: azure-functions/*/junit.xml,sdk/*/junit.xml

    # Custom coverage report configuration (Optional)
    # If not specified, defaults to ./coverage/coverage-summary.json
    junit-test-coverage-configuration: |
      http-cvw-algolia, azure-functions/http-cvw-algolia/coverage/coverage-summary.json
      http-cvw-application-form, azure-functions/http-cvw-application-form/coverage/coverage-summary.json
```
