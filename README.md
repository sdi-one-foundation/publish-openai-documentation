# publish-openai-documentation
A composite Github Action to automatically publish OpenAI Documentation for Single Digits services.


Example release.yaml that uses this action:

```yaml
name: Release

on:
  release:
    types: [published]

jobs:
  release:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Publish OpenAI Documentation
        uses: sdi-one-foundation/publish-openai-documentation@v1
        with:
          service-name: ${{ github.repository }}
          team-name: ${{ github.repository_owner }}
          file-output-path: "target/publishd-api/service-name.openapi.json"
```
