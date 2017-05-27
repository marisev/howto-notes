# Dummy Notes

## How to start working with ES6 in VSCODE

1. Install node
2. Install package manager: npm or yarn

## To transpile es6 to es5 from command line (and/or vscode terminal)
1. install babel command line package:
```
npm install -g babel-cli
```
   It is recomended to install it locally per project. 
   However in this example I do it globally for easier start and access through editor settings in multiple projects.

2. Add babel plugins:
```
npm install babel-preset-es2015 --save-dev
```
3. Create a .babelrc file in your project dir:
```
{
    "presets": ["es2015"]
}
```
Now you can transpile es6 to es5 from command line:
```
babel script.es6 --out-file script.js
```

## To auto-transpile on save in vscode:
1. Add "Run on Save" extension to your vscode
2. File>Preferences>Settings in User Settings part:
```
"emeraldwalk.runonsave": {
    "autoClearConsole": true,
    "commands": [
        {
            "match": "\\.es6$",
            "cmd": "cd ${fileDirname} && babel ${file} --out-file ../${fileBasenameNoExt}.js"
        }
    ]
}
```

"cmd" may be different, based on how you decide to organize your files
in this case it assumes you keep es6 scripts in /es6 folder with .es6 extension




[A good article to start](http://jamesknelson.com/the-six-things-you-need-to-know-about-babel-6/)