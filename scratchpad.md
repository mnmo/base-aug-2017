-----

## On a new project

```
export BASE="../base-aug-2017/"
```

-----

## .gitignore

[.gitignore][gitignore]

```
cp "$BASE.gitignore" .
```

-----

## Code formatting

```
npm i -D prettier
jq '.scripts.fmt="prettier --write --tab-width 4"' package.json | ex -sc 'wq!package.json' /dev/stdin
```

-----

## Flowtype

[.flowconfig][flowconfig]

```
cp "$BASE.flowconfig" .
npm i -D flow-bin
jq '.scripts.test="flow"' package.json | ex -sc 'wq!package.json' /dev/stdin
```

Backend

```
npm i -D flow-remove-types
```

Frontend

```
npm i -D unflowify

```
-----

## Config file / env vars

```
echo -e '[app]\nname = ""\n' > config-sample.toml
npm i -D cpy-cli
jq '.scripts.postinstall="cpy --no-overwrite --rename config.toml config-sample.toml ."' package.json | ex -sc 'wq!package.json' /dev/stdin
```

-----

## Bundling

```
npm i -D browserify
npm i -D unflowify tomlify es2040
```

-----

## Local static webserver

```
npm i -D http-server
"http-server docs"
```

-----

## Local browserify webserver

```
npm i -D budo
"budo --dir src --dir assets --force-default-index src/app.js -- " +
```

-----

## NPM Scripts

```
npm install nps nps-utils
npx nps init
```

-----

[gitignore]: https://github.com/mnmo/base-aug-2017/blob/master/.gitignore
[flowconfig]: https://github.com/mnmo/base-aug-2017/blob/master/.gitignore

