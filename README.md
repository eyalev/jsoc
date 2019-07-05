
# JSOC

JSON with comments

## Why

Demand [exists](https://stackoverflow.com/questions/244777/can-comments-be-used-in-json) for a file format which is strict as JSON but includes comments.

## Spec

Same as JSON, with hash-symbol (`#`) comments.

You're welcome :)

## Example

```yaml

# Based on JSON sample from: https://en.wikipedia.org/wiki/JSON#JSON_sample

{
    # Comment A
    "first_name": "John",
    "last_name": "Smith",
    "age": 25, # Comment B
    "address": {
        "street_address": "21 2nd Street",
        "city": "New York",
        "state": "NY",
        "postal_code": "10021"
    },
    # Comment C
    "phone_number": [
        {
            "type": "home",
            "number": "212 555-1234"
        },
        {
            "type": "fax",
            "number": "646 555-4567"
        }
    ],
    "gender": {
        "type": "male"
    },
    "human": true
}
# Comment D

```

## Implementation

Until we have a vibrant community and abundant libraries, the spec can be implemented with YAML.

### Python

```python
# Python 3
# Live example: https://repl.it/repls/JubilantTestyModularity

import yaml
import json
from pathlib import Path

text = Path('sample.jsoc.yaml').read_text()
jsoc = yaml.safe_load(text)  # Comments are not parsed
print(json.dumps(jsoc, indent=4))

```

Output:

```json

{
    "first_name": "John",
    "last_name": "Smith",
    "age": 25,
    "address": {
        "street_address": "21 2nd Street",
        "city": "New York",
        "state": "NY",
        "postal_code": "10021"
    },
    "phone_number": [
        {
            "type": "home",
            "number": "212 555-1234"
        },
        {
            "type": "fax",
            "number": "646 555-4567"
        }
    ],
    "gender": {
        "type": "male"
    },
    "human": true
}

```


