# Page 4 After GitHub Actions

We used GitHub Actions to deploy the MkDocs site automatically.

```
.github/workflows/ci.yml

name: ci
on:
  push:
    branches:
      - master
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-python@v2
        with:
          python-version: 3.8
      - run: pip install mkdocs mkdocs-material
      - run: mkdocs gh-deploy --force
```
