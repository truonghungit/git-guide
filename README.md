# Git Guide


## Install & config commitizen
- Install commitizen adapter
```
yarn add cz-conventional-changelog --dev
```

- add config to package.json
```
"config": {
	"commitizen": {
		"path": "cz-conventional-changelog"
	}
}
```

- add command to scripts in package.json
```
"scripts": {
    "commit": "cz"
}
```

Now we can run `yarn commit` or `npm run commit` instead of `git commit`


## Install & config commitlint

- Install commitlint with a config:
```
yarn add @commitlint/cli @commitlint/config-conventional --dev
```

- Create file `commitlint.config.js` with content
```
module.exports = {
  extends: ['@commitlint/config-conventional'],
};
```

- Install husky
```
yarn add husky --dev`
```

- Enable Git hooks
```
yarn husky install
```

- Add the commit-msg hook
```
yarn husky add .husky/commit-msg 'yarn commitlint --edit $1'
```
