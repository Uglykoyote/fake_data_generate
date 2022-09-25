Build status: [![Build Status](https://app.travis-ci.com/Uglykoyote/fake_data_generate.svg?branch=main)](https://app.travis-ci.com/Uglykoyote/fake_data_generate)
# fake_data_generate
Short how-to

1. git clone
2. docker build -f Dockerfile -t generatefakedatacsv:latest .
3. docker run -it --rm -v /tmp/:/tmp/ -e PERSON_COUNT=25 -e LOCALE=ru_RU generatefakedatacsv:latest
4. Result file will be placed in the /tmp/ directory.

If needed use an external template file, please follow the next example:
1. Copy `headers.json` to `custom_structure.json`. Remove/Add field(-s)
2. Execute command: docker run -it --rm -v /tmp/:/tmp/ -v $(pwd)/custom_structure.json:/app/custom_structure.json -e PERSON_COUNT=25 -e LOCALE=ru_RU -e JSON_TEMPLATE_FILE=custom_structure.json generatefakedatacsv:latest
3. Result file will be placed in the /tmp/ directory.

Check content with the command: `cat /tmp/persons.csv`