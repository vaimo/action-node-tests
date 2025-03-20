# GitHub Action for Node.js Tests

This action is used to execute tests in Node.js projects.

**Author:** Patryk Waluś (patryk.walus@vaimo.com)

## Supported Versions

- **v1**
    - Test execution action for Node.js projects.

## Usage

```yaml
- name: Run Tests
  uses: vaimo/action-node-tests@v1
  with:
    # Directories where JUnit report files are located (Optional)
    # If not specified, defaults to */junit.xml
    junit-test-report-path: azure-functions/*/junit.xml,sdk/*/junit.xml

    # Custom coverage report configuration (Optional)
    # If not specified, defaults to ./coverage/coverage-summary.json
    junit-test-coverage-configuration: |
      http-cvw-algolia, azure-functions/http-cvw-algolia/coverage/coverage-summary.json
      http-cvw-application-form, azure-functions/http-cvw-application-form/coverage/coverage-summary.json
```
