# Code-first using APIFlask

This is an example of using annotations in Python code - also known as "code-first design" - to generate an OpenAPI description.

## Pre-requisites

This is a Python application. You'll need Python 3 available, ideally at 3.12 or above with `virtualenv` and `pip` installed.

## Installation

First up you'll need to create a virtual environment and then activate it. Use your favorite environment manager like `pyenv`, or use the following boilerplate commands (assuming you are in this directory already):

```bash
virtualenv ./venv
source ./venv/bin/activate
```

With your fresh environment activated, you can install the dependencies using `pip`:

```bash
pip install -r requirements.txt
```

You are then set to run the application and generate the specification.

## Running the Application

To run the application and send requests to its API run the `flask` command with the `run` subcommand:

```bash
flask --app server:app run
```

You can then send a request to the API running on port 5000 using `curl` and format the output using a tool like `jq`:

```bash
curl http://localhost:5000/pets | jq '' -
```

Will give you the following response:

```bash
chapter-4-examples/code-first-using-apiflask ❮ on  main [!] curl http://localhost:5000/pets  | jq '' -
[
  {
    "id": 1,
    "name": "Barnaby",
    "tag": "Vicious"
  },
  {
    "id": 2,
    "name": "Colin",
    "tag": "Accountant"
  }
]
chapter-4-examples/code-first-using-apiflask ❯ on  main [!]
```

If you just want to regenerate the OpenAPI description document then you can run `flask` again with the `spec` subcommand:

```bash
flask --app server:app spec
```

Which will output a fresh copy of the document to stdout.

:thumbsup:
