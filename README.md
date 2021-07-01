# @joebowbeer/regsync
Publish package versions from one registry into another.

## Setup
`npm install`
`npm run build`

## Using the script

```shell script
node ./dist/cli.js --name @scope/pkgname \
 --from.registry https://registry.npmjs.org/ --from.token $NPM_TOKEN \
 --to.registry https://npm.pkg.github.com --to.token $GITHUB_TOKEN
```

This will migrate all the versions that it can find on the "FROM.REGISTRY" that are missing on the "TO.REGISTRY"

If new versions of the package are published to the ORIGIN registry, they'll need to be migrated again in the future.

I'td be best to ensure that the package you're dealing with is automatically published to the new registry as part of its CI process.
