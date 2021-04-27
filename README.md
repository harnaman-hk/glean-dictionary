# Glean Dictionary

[![CircleCI](https://circleci.com/gh/mozilla/glean-dictionary.svg?style=svg)](https://circleci.com/gh/mozilla/glean-dictionary)

The Glean dictionary aims to provide a comprehensive index of datasets generated
inside Mozilla for applications built using the
[Glean SDK](https://mozilla.github.io/glean/book/index.html).

This project is under active development. For up to date information on project
structure and governance, see:

https://wiki.mozilla.org/Data/WorkingGroups/GleanDictionary

You can play with an early version of the Glean Dictionary at:

https://dictionary.protosaur.dev

## Getting Started

You should be able to create your own local copy of the dictionary so long as
you have [Python](https://www.python.org/) (version 3.8) and
[node.js](https://nodejs.org/) installed. Follow these instructions:

```bash
# Create and activate a python virtual environment.
python3 -m venv venv/
source venv/bin/activate
pip install -r requirements.txt

# Build data needed by dashboard
./scripts/build-glean-metadata.py

# Install npm dependencies and start a local
# instance of the GUI
npm install
npm run dev
```

If that worked, you should be able to see a local version of Glean at
http://localhost:5000

## Contributing

For more information on contributing, see [CONTRIBUTING.md](./CONTRIBUTING.md)
in the root of this repository.
