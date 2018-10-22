# EnvTools - ESLint

## Description

The intention of this document is to save the steps and files related to the ESLint configuration for Linux (It has been configured in Linux Mint 19 Only).

## Installation

### Configure npm global directory

This will not work with nvm, but nvm will take care of this for you ! In this situation the globally installed package will be in /usr/local/lib/node_modules and owned by the user who installed them.

We will change the directory where npm makes global installations:

```shell
$ mkdir ~/.npm-global # directory where npm will install packages
$ npm config set prefix '~/.npm-global' # configure npm
$ echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.profile #add directory to path
$ source ~/.profile # refresh path for current session
```

It should be working now. You can try it by running

```shell
$  npm install -g jshint
```

without sudo !
Enable npm completion

Just run:

```shell
$  npm completion >> ~/.bashrc
```

### Install ESLint

#### Global:

`npm i -g eslint`

#### Project scope:

`npm install eslint --save-dev`

### Setup configuration

#### Global:
`eslint --init`

#### Project scope
Run `eslint --init` from the node_module/eslint/bin folder created in the project.

####Example of the configuration

[.eslintrc.json](.eslintrc.json)

### Configure for Sublime Text 3:

0. It is suggested to complete the above steps before configuring in Sublime Text  

1. Install Package Control, the steps can be found here: https://packagecontrol.io/installation
2. Install SublimeLinter, https://packagecontrol.io/packages/SublimeLinter
3. Install Sublime​Linter-eslint, https://packagecontrol.io/packages/SublimeLinter-eslint
4. <Optional> Install ESLint package, https://packagecontrol.io/packages/ESLint
	* Go to “Preferences / Package Settings / ESLint / Settings - User” to add your custom settings or in case the system is not taking the environment tools as expected.
	* Example can be found here: [ESLint.sublime-settings](ESLint.sublime-settings)