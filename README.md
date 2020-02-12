## Install Npm on Mac
First, install brew
``` bash
#Install Home-brew
$ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

#uninstall Hone-brew
uby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall)"
```
Second, uninstall node and nvm which were installed by brew.
``` bash
$brew uninstall --force node
$brew uninstall --force nvm
```
Next, install nvm
```bash
$touch ~/.bashrc
$curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash
$source ~/.bashrc
$command -v nvm 
```
If the above doesn't fix the problem, open your `~/.bash_profile` and add the following line of code:\
`source ~/.bashrc`\
Refer to https://github.com/creationix/nvm#install-script

Last, install node
```bash
$nvm --version
# check installed nodes
$nvm ls
# for remote 
$nvm ls-remote --lts
# To download, compile, and install the latest release of node, do this:
$nvm install node
# for sepecific version name
$nvm install v8.9.4
$nvm use v8.9.4
#just use the installed version
$nvm use node
# set default node version
$nvm alias default v8.10.0
```
## Usage
All packages can be founded in https://www.npmjs.com/
### Command
#### npm init
To make package.json
```bash
# -y default config 
$ npm init -y
```
#### npm install
All packages in package.json is supposed to install into node_modules
```bash
$ npm install
# Install lodash package[version name] and add it into dependencies
$ npm i lodash@4.17.4
# Install lodash and react
$ npm i lodash react
# The package will appear in  devDependencies
$ npm install node-tap --save-dev
# Install package globally,add it in ~/.nvm/versions/node/v8.10.0/lib/node_modules/create-react-app
$ npm install -g crate-react-app
```
#### npm ci
`npm install` can change package-lock.json because of npm version, different platform or somthing.\
`npm ci` has node_modules intalled by only using package-lock.json. package-lock.json and package.json is different, throw an erors\
Required  npm 5.7.1 

``` bash
$ npm ci
```
#### npm ls
Show packlages installed
```bash
$ npm ls
# for global
$ npm ls -g
```
#### npm outdated
Show outdated package
```bash
$ npm outdated
# for global
$ npm outdated -g
```
#### npm update
Update all packages outdated
```bash
# according to package.json
$ npm update
$ npm install lodash@latest
```
#### npm uninstall package
Remove package form node_modues
```bash
$ npm uninstall lodash
``` 
### Script
npm supports the "scripts" property of the package.json file,
```javascript
{
  "name": "lookup-server",
  "version": "0.0.1",
  "private": true,
  "babel": {
    "presets": [
      "es2015",
      "stage-0"
    ]
  },
  "dependencies": {
    "babel-cli": "6.22.2",
    "babel-core": "6.22.1",
    "babel-preset-es2015": "6.22.0",
    "babel-preset-stage-0": "6.22.0",
  },
  "scripts": {
    "start": "npm run server",
    "server": "babel-node start-server.js"
  }
}

```
```bash
# pretest, test, posttest
$ npm test
prestop, stop, poststop
$ npm stop
prestart, start, poststart
$ npm start 
prerestart, restart, postrestart
$ npm restart
$ npm run server
```

Refer https://docs.npmjs.com/
