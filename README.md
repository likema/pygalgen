# Pygal generation tool

A tool for generating SVG or PNG chart by YAML or JSON.

## Prerequisites

Python 3

```bash
pip install pyyaml pygal cairosvg
```

## Usage

```
usage: pygalgen [-h] [--list-styles] [-t {svg,png,html}] [-j JS] [-s STYLE]
                [-o OUTPUT]
                [yaml]

positional arguments:
  yaml                  YAML or JSON config, default STDIN

optional arguments:
  -h, --help            show this help message and exit
  --list-styles         List all available styles.
  -t {svg,png,html}, --type {svg,png,html}
                        Output type, default output file extension or svg if
                        not specified output
  -j JS, --js JS        Javascript file, effective when type is PNG
  -s STYLE, --style STYLE
                        Style name, override style name only when trailing
                        with a "!", override entire style when trailing with
                        two "!"
  -o OUTPUT, --output OUTPUT
                        Output SVG or PNG file, default STDOUT
```

## Sample YAML

```yaml
type: Line
title: Browser usage evolution
x: [2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010, 2011, 2012]
y: [5, 10, 15, 20, 30, 40, 50, 60, 70, 80, 90, 100]
series:
  - [Firefox, ~, ~, 0, 16.6, 25, 31, 36.4, 45.5, 46.3, 42.8, 37.1]
  - [Chrome, ~, ~, ~, ~, ~, ~, 0, 3.9, 10.8, 23.8, 35.3]
  - [IE, 85.8, 84.6, 84.7, 74.5, 66, 58.6, 54.7, 44.8, 36.2, 26.6, 20.1]
  - [Others, 14.2, 15.4, 15.3, 8.9, 9, 10.4, 8.9, 5.8, 6.7, 6.8, 7.5]
```

See more:

* [Simple style sample](test.yaml)
* [Style config sample](test_style.yaml)
* [Simple series sample](test_series.yaml)
