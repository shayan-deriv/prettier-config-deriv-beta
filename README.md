# eslint-config-deriv
This package provides Deriv's .prettierrc as an extensible shared config.

# installation

### For **deriv-com:**


 1. remove `"prettier": "^2.5.1"` from package.json in root and also each packages:

 2.  Install the latest version:

    npm i -D prettier-config-deriv

### For **deriv-app:**


 1. remove `"prettier": "^2.1.2",` from package.json:

 2.  add the below to the **devDependencies** of the root `package.json`:

	"prettier-config-deriv": "^1.0.0-beta.0"

 3.  run `npm run i` and then `npm run bootstrap`

# Usage

### For **deriv-com:**


rename `.prettierrc` to `.prettierrc.js` and import the package inside your config:
```
module.exports = {
    ...require('prettier-config-deriv'),
    overrides: [
        {
            files: ['crowdin/messages.json', 'src/translations/*.json'],
            options: {
                tabWidth: 2,
            },
        },
    ],
};
```
You can override any options in a way that suits your code styles.

Run the bellow command to test it:

    npm run format

**note  that** since we renamed our config file you need to modify prettier command in package.json as well.


### For **deriv-app:**

rename `.prettierrc` to `.prettierrc.js` and import the package inside your config:
```
module.exports = {
    ...require('prettier-config-deriv'),
};
```

Run the bellow command to test it:

    npm run prettify

**note  that** since we renamed our config file you need to modify prettier command in package.json as well.