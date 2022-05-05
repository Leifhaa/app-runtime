# DHIS2 Application Runtime

[![npm](https://img.shields.io/npm/v/@dhis2/app-runtime.svg)](https://www.npmjs.com/package/@dhis2/app-runtime)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

Docs are available at [runtime.dhis2.nu](https://runtime.dhis2.nu).

## Development

```sh
> yarn test # runs yarn test on each directory under ./services, and also in ./runtime
> yarn build # runs yarn build on each directory under ./services, and then in ./runtime
> yarn start # builds all services, builds the runtime, and starts the query playground server
```

## Examples

A `create-react-app` example is available at [./examples/cra](./examples/cra). If running `yarn install` locally in the example directory, be sure to run it with `yarn install --force --check-files` so that it pulls in the runtime (specified as a `file:` dependency).

A query REPL platform application is also available at `./examples/query-playground`.

Running `yarn build` at root will automatically update the example app's copy, and running `yarn start` will build the runtime and then start the example.

A [`DHIS2 App Platform`](https://platform.dhis2.nu) example is available at [./examples/query-playground](./examples/query-playground). This is a full, deployable DHIS2 application and a live standalone version is available at [runtime.dhis2.nu/playground](https://runtime.dhis2.nu/playground)

## Release

Releases run automatically for every commit to the master branch using the [d2 cli](https://github.com/dhis2/cli).

**NEVER PUSH DIRECTLY TO `master`! ALL DEVELOPMENT IN THIS REPOSITORY IS THROUGH PULL REQUESTS**

## Report an issue

The issue tracker can be found in [DHIS2 JIRA](https://jira.dhis2.org)
under the [LIBS](https://jira.dhis2.org/projects/LIBS) project.

Deep links:

-   [Bug](https://jira.dhis2.org/secure/CreateIssueDetails!init.jspa?pid=10700&issuetype=10006&components=11024)
-   [Feature](https://jira.dhis2.org/secure/CreateIssueDetails!init.jspa?pid=10700&issuetype=10300&components=11024)
-   [Task](https://jira.dhis2.org/secure/CreateIssueDetails!init.jspa?pid=10700&issuetype=10003&components=11024)




### How To develop:
1. Go to root folder and type:
```
npx dhis-portal --target=https://verify.dhis2.org/2.37dev/
```

Now we've made a procy from http:localhost:9999 to a development server of DHIS

2.
In root folder, run command:
```
yarn start
```
(Note; I had to run this twice as it had error in first run)

3. Go to the page:
   - http://localhost:3000/
    use the fields:
     - Server: http://localhost:9999
     - Username: admin
     - Password: district
   
4. Do changes, and refresh page after changes! :)

5. For debugging, the source files can be found under  Localhost:3000/static/js/C/users....../.d2/shell/src/D2App/{Anything here, e.g components}

### Notes about implementation:
The playground input field's is based on react-ace (https://github.com/securingsincity/react-ace/tree/main)
It means that much of the heavy weight is already done by this framework.
Pro's using it:
    - We're getting alot "for free"
    - Its already based upon it
    - Its open source, so it's possible to extend
    - It has advanced features such as auto complete (example here, Enable Live AUtocomplete & Basic Autocomplete: https://securingsincity.github.io/react-ace/)
    - Not only does it support modules such as query's but it also supports creating javascript code in general. It means that we can use this playground to do API calls
    but we can also use this playground to create javascript code & even javascript code + API calls all together :)
Cons:
    - I have to adapt their source code if i wanna do changes


As it stands now, I believe its a good idea actually using their framework, but Ill need to research this more throughly.

Todo's:
- Lage en fork slik at jeg faktisk kan pushe til github!
- Ace supporter ikke lengre brace fra versjon 8. Jeg bør nok oppdatere til siste versjon og slette bruk av brace.
- Må spørre Austin om jeg faktisk editer det prosjektet som currently supporter playgrounden. -> AVVENTER SVAR...


