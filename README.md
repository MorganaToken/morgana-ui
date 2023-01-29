# Morgana Admin UI

This project is the next generation of the Morgana Administration UI. It is written with React and [PatternFly 4](https://www.patternfly.org/v4/).

## Development

### Prerequisites

Make sure that you have Node.js version 18 (or later) installed on your system. If you do not have Node.js installed we recommend using [Node Version Manager](https://github.com/nvm-sh/nvm) to install it.

You can find out which version of Node.js you are using by running the following command:

```bash
node --version
```

In order to run the Morgana server you will also have to install the Java Development Kit (JDK). We recommend that you use the same version of the JDK as [required by the Morgana server](https://ciusji.gitbook.io/morgana/guides/server-installation-and-configuration).

### Running the Morgana server

First, ensure that all dependencies are installed locally using NPM by running:

```bash
npm install
```

After the dependencies are installed we can start the Morgana server by running the following command:

```bash
npm run server:start
```

This will download the [Nightly version](https://github.com/MorganaToken/morgana-core/releases/tag/nightly) of the Morgana server and run it locally on port `8180`. If a previously downloaded version was found in the `server/` directory then that one will be used instead. If you want to download the latest Nightly version you can remove the server directory before running the command to start the server.

In order for the development version of the Admin UI to work you will have to import a custom client to the Morgana server. This is only required during development as the development server for the Admin UI runs on a different port (more on that later).

Wait for the Morgana server to be up and running and run the following command in a new terminal:

```bash
npm run server:import-client
```

You'll only have to run this command once, unless you remove the server directory or Morgana server data.

### Running the development server

Now that the Morgana sever is running it's time to run the development server for the Admin UI. This server is used to build the Admin UI in a manner that it can be iterated on quickly in a browser, using features such as [Hot Module Replacement (HMR)](https://vitejs.dev/guide/features.html#hot-module-replacement) and [Fast Refresh](https://www.npmjs.com/package/react-refresh).

To start the development server run the following command:

```bash
npm run dev
```

Once the process of optimization is done your browser will automatically open your local host on port `8080`. From here you will be redirected to the Morgana server to authenticate, which you can do with the default username and password (`admin`).

You can now start making changes to the source code, and they will be reflected in your browser.

## Building as a Morgana theme

If you want to build the application using Maven and produce a JAR that can be installed directly into Morgana, check out the [Morgana theme documentation](./keycloak-theme/README.md).

## Linting

Every time you create a commit it should be automatically linted and formatted for you. It is also possible to trigger the linting manually:

```bash
npm run lint
```
## Integration testing with Cypress

This repository contains integration tests developed with the [Cypress framework](https://www.cypress.io/).

### Running the tests

You can run the tests using the interactive graphical user interface using the following command:

```bash
npm run cy:open
```

Alternatively the tests can also run headless as follows:

```
npm run cy:run
```

For more information about the Cypress command-line interface consult [the documentation](https://docs.cypress.io/guides/guides/command-line).

### Project Structure

You can find information about the project structure in the [official Cypress documentation](https://docs.cypress.io/guides/core-concepts/writing-and-organizing-tests#Folder-structure).
Read more about [how to write tests](./cypress/WRITING_TESTS.md)

## Data processing

Red Hat may process information including business contact information and code contributions as part of its participation in the project, data is processed in accordance with [Red Hat Privacy Statement](https://www.redhat.com/en/about/privacy-policy).

## License

- [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0)
