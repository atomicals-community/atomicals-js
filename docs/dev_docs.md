# Documentation for Atomicals-js developper

This documentation is intended to help contributors organisation and tips to maintain it. 

### Publishing to npm

To publish a new version of `atomicals-js` to the npm registry:

#### 1. Build the package

```bash
npm run build
```

If you're using local patches for development:

```bash
npm run postinstall:dev
```

#### 2. Update the version

Use semantic versioning:

```bash
npm version patch   # bugfix
npm version minor   # new feature
npm version major   # breaking change
```

#### 3. Publish to npm

```bash
npm publish --access public
```

For testing preview versions:

```bash
npm publish --access public --tag next
```

Install the preview version with:

```bash
npm install atomicals-js@next
```

#### 4. Push changes to GitHub

```bash
git push origin main --tags
```

You can preview the contents of the published package with:

```bash
npm pack
```

Make sure `dist/` is built and correctly included before publishing.

