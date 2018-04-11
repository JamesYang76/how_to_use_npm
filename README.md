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

#### npm init
To make package.json
```bash
# -y default config 
$ npm init -y
```
#### npm install
All packages is supposed to install in package.json.
```bash
$ npm install
# Intall lodash package[version name] and add it into dependencies
$ npm i lodash@4.17.4
# The package will appear in  devDependencies
$ npm install node-tap --save-dev
# Install package globally,add it in ~/.nvm/versions/node/v8.10.0/bin/create-react-app
$ npm install -g crate-react-app
```
