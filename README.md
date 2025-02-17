# Minify-Web (WIP)

## Presentation

Work in progress, do not use.
This github action minifies and uglifies html, js and css files from a given directory to another.

## License
[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/jtbonhomme/minify-js/blob/master/LICENSE) 

## Version
[![GitHub Release](https://img.shields.io/github/v/release/jtbonhomme/minify-js?include_prereleases)]()

### Usage
First you need to check out your repository, then configure the Minify-JS job, at the end you can commit to your repository.
Below is an example of how to do all of this.

```yaml
name: Minify Workflow
on:
  push:
    branches: [ master ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      # Checks-out your repository
      - uses: actions/checkout@v2
        with:
          ref: ${{ github.ref }}

      # Job for Minify-JS
      - name: Web minifier
        uses: jtbonhomme/minify-js@v0.5
        with:
          directory: 'src'
          output: 'dist/'
          
      # Auto-commit to repository
      - uses: stefanzweifel/git-auto-commit-action@v4
        with:
          commit_message: 'Minify-JS : Commit Pipeline'
          branch: ${{ github.ref }}
```
