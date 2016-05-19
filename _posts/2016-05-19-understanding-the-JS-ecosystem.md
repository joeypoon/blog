---
layout:     post
title:      "Understanding the JS ecosystem as a Rubyist (Part 1)"
subtitle:   "npm"
date:       2016-05-19
author:     "Joey F. Poon"
header-img: "img/home-bg.jpg"
---
### These are my confessions
I have a confession. I have been cheating when it comes to React. I have just been throwing it into my Rails projects. While this works for most of my use cases, it really has just been an excuse to not learn the front-end ecosystem. It's scary. There are so many words being thrown around when it comes to JS that it can get a little intimidating. Well, I finally sat down and learned what I really need for just the basics.

### Getting started with npm
To get started, the first thing you need is npm. npm stands for **N**ode **P**ackage **M**anager and is used for installing JS packages or modules (package and module can be used interchangeably). Packages are like gems. So npm is basically a gem manager. Unlike gems, you have to first initialize your project for npm with `$ npm init`. This will create a package.json file which keeps track of the packages you installed in this project. This way, when someone else clones your project, their npm knows what packages to install to make the project run.

### Installing Packages
After you initialize your project you can install packages using `$ npm install packageName`. What this does is install the package to a directory in your project root called node_modules (You should add this to your .gitignore). In addition, if you add the --save flag `$ npm install packageName --save`, it will automatically add the package to your package.json file.

### Global install
Unlike `$ gem install gemName` which is a global install that you can access anywhere, npm install is a local install. You can only use the package in the directory you installed it. If needed, you can add the optional -g flag to save a package globally `$ npm install -g packageName`.

### Scripts
In your package.json, you can add npm scripts. These are basically terminal aliases. You can run them using `$ npm run scriptName`. An example use case would be for tests `$ npm run tests`.
```
// projectRoot/package.json
{
  "scripts": {
    "scriptName": "some terminal command",
  }
}
```

It's now 1:20 AM so I am going to call it a night here. Stay tuned for part 2!
