# Workflows
This project is a combination of three GitHub Action Workflows commonly used in BBOP projects.
- Quality Check (qc)
- Autodeployment of documentation
- PyPI Release


# Usage

## For qc
Assuming `build` in the workflow looks like this:
```
build:
    runs-on: ubuntu-latest
    strategy:
        matrix:
        python-version: [ "3.9", "3.10" ]
```

```
- uses: hrshdhgd/qc-action@main
  with:
    python-versions: ${{ matrix.python-version }}
    use-tox: true
    workflow-type: qc
```

## For docs
```
- uses: hrshdhgd/qc-action@main
  with:
    python-versions: "3.9"
    workflow-type: docs
    token: ${{ secrets.GH_TOKEN }}
```

## For PyPI
```
- uses: hrshdhgd/qc-action@main
  with:
    python-versions: "3.9"
    workflow-type: pypi
    token: ${{ secrets.PYPI_TOKEN }}

```