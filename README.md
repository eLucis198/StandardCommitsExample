# This repo is a standard commits example.

---

* **Commitlint: Checks if the commit message meet the conventional commit format**
* **Husky: To lint commits before they are created**
* **Commitizen: When you commit, you'll be prompted to fill out any required commit fields at commit time.**

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
# Install Husky
npm install husky@7.0.4 --save-dev

# Active hooks
npx husky install

# Add hook
cat <<EEE > .husky/commit-msg
#!/bin/sh
. "\$(dirname "\$0")/_/husky.sh"

npx --no -- commitlint --edit "\${1}"
EEE
```

## [Commitizen](https://github.com/commitizen/cz-cli)

> When you commit with Commitizen, you'll be prompted to fill out any required commit fields at commit time.

```
# Install commitizen
npm install --save-dev commitizen

# initialize the conventional changelog adapter
npx commitizen init cz-conventional-changelog --save-dev --save-exact
```

## [standard-version](https://github.com/conventional-changelog/standard-version)

```
npm i --save-dev standard-version
```