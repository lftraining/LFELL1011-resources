# Code-first using springdoc-openapi

This is an example of using annotations in code - also known as "code-first design" - to generate an OpenAPI description.

## Pre-requisites

This is a Java application. You will need Java 17 installed, with instructions dependent on your operating system.

Once installed or located ensure that `$JAVA_HOME` or `$JAVA_HOME` is set and that `java` is added to your PATH (with the approach depending on your operating system).

## Installation

With Java 17 available you should be able to run `gradle` or `gradlew` to install any dependencies.

Assuming you are already in this directory, simply run:

```bash
./gradlew
```

And you should be good to go.

## Running the Application

To run the application and send requests to its API run the `bootRun` command:

```bash
./gradlew bootRun
```

You can then send a request to the API running on port 8080 using `curl` and format the output using a tool like `jq`:

```bash
curl http://localhost:8080/pets | jq '' -
```

Will give you the following response:

```bash
chapter-4-examples/code-first-using-springdoc-openapi ❮ on  main [!] curl http://localhost:8080/pets  | jq '' -
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
chapter-4-examples/code-first-using-springdoc-openapi ❯ on  main [!]
```

If you just want to regenerate the OpenAPI description document then you can run the following command:

```bash
./gradlew clean generateOpenApiDocs
```

Which will output a fresh copy of the document to `./build/openapi/code-first-openapi.yaml`.

:thumbsup:
