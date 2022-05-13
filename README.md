# This repo is a standard commits example.

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

---

## [Husky](https://github.com/typicode/husky)

> To lint commits before they are created you can use Husky's `commit-msg` hook:

```sh
# Install Husky v6
npm install husky --save-dev
# or
yarn add husky --dev

# Activate hooks
npx husky install
# or
yarn husky install
```