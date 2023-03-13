# GoTest JSON to JUnit XML

GoTest JSON to JUnit XML is a GitHub Action that converts GoTest JSON to JUnit XML.

## Inputs

* `input`: The input GoTest JSON file. Required.
* `output`: The output JUnit XML file. Required.

## Example Usage

Here's an example workflow that uses the GoTest JSON to JUnit XML action:

```yml
name: Test

on: push

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Run tests
        run: go test -v -json | tee gotest.json

      - name: Convert GoTest JSON to JUnit XML
        uses: pl-strflt/gotest-json-to-junit-xml@v1
        with:
          input: 'gotest.json'
          output: 'junit.xml'
```

This workflow checks out the code, runs the tests using `go test`, and then converts the GoTest JSON report to JUnit XML report.

---
