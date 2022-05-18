# This repo is a standard commits example.

---

<h1 align="center">STANDARD COMMITS</h1>

* **[Commitlint](#Commitlint): Checks if the commit message meet the conventional commit format**
* **[Husky](#Husky): To lint commits before they are created**
* **[Commitizen](#Commitizen): When you commit, you'll be prompted to fill out any required commit fields at commit time**

---

## [Commitlint](https://github.com/conventional-changelog/commitlint/)

> commitlint checks if your commit messages meet the [conventional commit format](https://conventionalcommits.org).

### Version Support and Releases

- Node.js [LTS](https://github.com/nodejs/LTS#lts-schedule) `>= 12`
- git `>= 2.13.2`

### Getting started

```sh
# Install commitlint cli and conventional config
npm install --save-dev @commitlint/{config-conventional,cli}
# For Windows:
npm install --save-dev @commitlint/config-conventional @commitlint/cli

# Configure commitlint to use conventional config
echo "module.exports = {extends: ['@commitlint/config-conventional']}" > commitlint.config.js
```

Note: 
The command above created the config file with Encoding UFT-16 LE. I was not able to execute commitlint with the file as UFT-16 LE.

Some commands to test commitlint

```sh
# Should throw an error
echo "test commit: this is a test commit" | npx commitlint

# Will check your last commit
npx commitlint --from HEAD~1 --to HEAD --verbose
```

---

## [Husky](https://github.com/typicode/husky)

> To lint commits before they are created you can use Husky's `commit-msg` hook:

```
# Install Husky v7
npm install husky@7.0.4 --save-dev

# Active hooks
npx husky install

# Add hook
npx husky add .husky/commit-msg 'npx commitlint --edit $1'
```

## [Commitizen](https://github.com/commitizen/cz-cli)

> When you commit with Commitizen, you'll be prompted to fill out any required commit fields at commit time.

```
# Install commitizen
npm install --save-dev commitizen

# initialize the conventional changelog adapter
npx commitizen init cz-conventional-changelog --save-dev --save-exact
```

```
# This config should be on package.json
"config": {
    "commitizen": {
      "path": "cz-conventional-changelog"
    }
  }
```

run `npx cz` innitiate the commit process with commitizen

---

<h1 align="center">CHANGELOG</h1>

---

* **[Standard-version](#Standard-version): Used to generate automatic CHANGELOG based on conventional commits**

---

## [standard-version](https://github.com/conventional-changelog/standard-version)

> A utility for versioning using [semver](https://semver.org/) and CHANGELOG generation powered by [Conventional Commits](https://www.conventionalcommits.org/en/).

```
npm install standard-version --save-dev
```

Npm run script
```
{
  "scripts": {
    "release": "standard-version"
  }
}
```

The relation with semantical-commits is the following

MAJOR => BRAKING CHANGE
MINOR => FEAT
PATCH => FIX


Some scripts

```
To run genereate changelog for first release
npm run release -- --first-release

To generate changelog
npm run release

Publish
npm publish --tag next
```

If you want to control the version manually

```
# Pre-release | Generates version 1.0.1-0
npm run release -- --prerelease

# Specific name | Generates 1.0.1-alpha.0
npm run release -- --prerelease alpha

# Major | Bumps Major - 1.0.0 => 2.0.0
npm run release -- --release-as major

# Minor | Bumps Minor - 1.0.0 => 1.1.0
npm run release -- --release-as minor

# Patch | Bumps Patch - 1.0.0 => 1.0.1
npm run release -- --release-as patch
```
