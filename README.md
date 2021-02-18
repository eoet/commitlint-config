# @eoet/commitlint-config

## Installation

**yarn**
```sh
yarn add --dev @commitlint/cli @episerver/commitlint-config
```

**npm**
```sh
npm install --save-dev @commitlint/cli @episerver/commitlint-config
```

## Usage

Configure commitlint to use the eoet configuration via a `commitlint.config.js` file or a `commitlint` field in `package.json`.

**commitlint.config.js**
```js
module.exports = {
    extends: ['@eoet']
};
```

**package.json**
```json
"commitlint": {
    "extends": ["@eoet"]
}
```

## Commit Message Format

Commits should adhere to the following format:

```
<type>(<scope>): <subject>

<body>

<footer>

<references>
```

The following rules apply to the above format:

1. A commit message consists of a header, body, footer, and references.
1. The header is the only mandatory part of the commit message.
1. The header must have a type and a subject; scope is optional.
1. Scope should be surrounded by parenthesis; otherwise they are omitted.
1. The type and scope should be lower case.
1. The subject and body should be sentence case.
1. The subject should not end with a dot.
1. The header line is limited to 72 characters.
1. Any other line should be wrapped at 100 characters.

### Types

Must be one of the following:

| Type | Description |
| --- | --- |
| chore | Build process or auxiliary tool changes |
| docs | Documentation only changes |
| feat | A new feature |
| fix | A bug fix |
| refactor | A code change that neither fixes a bug or adds a feature |
| release | Create a release commit |
| revert | Revert a previous commit |
| test | Add missing tests |

#### Revert

If the commit reverts a previous commit, it should begin with `revert: `, followed by the header of the reverted commit. In the body it should say: `This reverts commit <hash>.`, where the hash is the SHA of the commit being reverted.

### Footer

The footer should only contain information about breaking changes and should use the following format:

```
BREAKING CHANGE: <description>
```

The description should be a concise explanation of the breaking change. The body can be omitted if the breaking change description and subject give enough information to understand the commit.
