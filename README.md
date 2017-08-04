# base-aug-2017
JS dev in august 2017

## Tools Choices Summary

Inspirations: 
[@substack][substack], 
[@sindresorhus][sindresorhus],
[@dominictarr][dominictarr],
[@dan_abramov][abramov], 
[@yoshuawuyts][yoshua], 
[@chenglou][chenglou],
[@jlongster][jlongster],
[@facebook][facebook]

- Code editor: [vim][vim] / [neovim][neovim]
- Time sheet: [timetrap][timetrap]
- Makefile / task runner: [npm scripts with nps][nps]
- Front-end bundler: [browserify][browserify]
- ES6, 7, next features: [es2040][es2040]
- Type checking: [flow][flow]
- Code Formating: [prettier][prettier]
- Configuration / env vars: [toml][toml]
- Front-end framework: [choo][choo]
- Database: [leveldb][leveldb]
- API: [graphql][graphql]
- Dev webserver: [budo][budo]
- Static webserver: [http-server][http-server]
- Local Tunner: localtunnel.me
- SSL: Lets Encrypt
- Static host: [github pages][ghpages]

[substack]: https://github.com/substack
[sindresorhus]: https://github.com/sindresorhus
[dominictarr]: https://github.com/dominictarr
[yoshua]: https://github.com/yoshuawuyts
[chenglou]: https://github.com/chenglou
[jlongster]: https://github.com/jlongster
[abramov]: https://github.com/gaearon
[facebook]: https://github.com/facebook
[vim]: http://www.vim.org/
[nvim]: https://neovim.io/
[timetrap]: https://github.com/samg/timetrap
[nps]: https://github.com/kentcdodds/nps
[browserify]: http://browserify.org/
[es2040]: https://github.com/ahdinosaur/es2040
[flow]: https://flow.org/
[prettier]: https://github.com/prettier/prettier
[toml]: https://github.com/toml-lang/toml
[choo]: https://github.com/choojs/choo
[budo]: https://github.com/mattdesl/budo
[httpserver]: https://github.com/indexzero/http-server
[ghpages]: https://pages.github.com/
[leveldb]: http://leveldb.org/
[graphql]: http://graphql.org/

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

