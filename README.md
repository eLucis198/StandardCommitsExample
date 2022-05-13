# This repo is a standard commits example.

---

## Commitlint

commitlint checks if your commit messages meet the [conventional commit format](https://conventionalcommits.org).

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