# Contributing

## Prepare a new release for `@rescript/std`

Build a (temporary) ReScript project with the `rescript` version you want to publish:

```
mkdir ../temp-project
cd ../temp-project

npm init -y
npm install rescript@x.y.z --save

npx rescript init
npx rescript
```

Now copy over the new runtime files to our `lib` directory:

```
# Go back to the std project
cd ../std
rm -rf lib/es6
rm -rf lib/js

# Copy the runtime files
cp -R ../temp-project/node_modules/rescript/lib/es6 lib
cp -R ../temp-project/node_modules/rescript/lib/js lib

# Check the diffs and if everything looks fine, check in the changes
git add lib
git commit -m "Update changes for x.y.z"
```

## Publish to `npm`

> **Note:** You will need npm publishing rights for the `@rescript` org to do
> that. Ping the maintainers if you need someone to cut a new release.

```
# Use npm version to bump the `package.json` version, create a new release commit and add a new tag
npm version x.y.z

# Push the release commit + tags
git push && git push --tags

# Run the publishing process
npm publish
```
