# actions_python_bandit
A Github action for security scanning with bandit.


<br/>

## How to use
In your .github/workflows directory, create a yaml file (such as main.yaml). Add a job for each desired workflow with the `uses` keyword. Use the `with` keyword to pass any desired variables.

Examples:

```
on: [push]

jobs:
  bandit:
    runs-on: ubuntu-latest
    name: "bandit"
    steps:
      - uses: davidslusser/actions_python_bandit@v1.0.0
```
<br/>

```
on: [push]

jobs:
  bandit:
    runs-on: ubuntu-latest
    name: "bandit"
    steps:
      - uses: davidslusser/actions_python_bandit@v1.0.0
        with:
          src: "src"
          options: "-r"
          pip_install_command: "pip install -e .[dev]"
          python_version: "3.9"
```

<br/>

## Inputs
  - **src:** source directory of code to check (defaults to "`.`")
  - **options:** optional flags/parameters used in bandit command (defaults to "`-r`")
  - **pip_install_command:** pip install command (defaults to "`pip install bandit`")
   - **python_version:** version of python to run workflow with (defaults to "`3.x`")


<br/>

## References
 - https://bandit.readthedocs.io/en/latest/
 - https://pypi.org/project/bandit/
