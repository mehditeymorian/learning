# Node.js Package Manager CLI

### What is _package.json_?
As a general rule, any project that's using Node.js will need to have a _package.json_ file.

At its simplest, a _package.json_ file can be described as a manifest of your project that includes the packages and applications it depends on, information about its unique source control, and specific metadata like the project's name, description, and author.

The other majorly important aspect of a _package.json_ is that it contains a collection of any given project's dependencies. These dependencies are the modules that the project relies on to function properly.

[Checkout](package.json) the structure of a simple _package.json_ file.

### Initialize a Project
the following command will create a _package.json_ file for you
```shell
npm init
```

### Instantly Initialize a Project
if you want to get on to building your project, and don't want to spend the (albeit brief) time answering the prompts that come from npm init, you can use the following command
```shell
npm init --yes
```

### Installing Modules
you can install modules with the following command
```shell
npm install <module>
npm i <module>
```

example
```shell
npm install express
```

in addition to triggering an install of a single module, you can actually trigger the installation of all modules that are listed as dependencies and devDependencies in the package.json in the current directory. To do so, you'll simply need to run the command itself
```shell
npm install
npm i
```

### Install Modules and Save
Install modules and save them to your package.json as a dependency
```shell
npm install <module> --save
npm install <module> --save-dev
```

### Install Modules Globaly
```shell
npm install <module> --global
npm install <module> -g 
```

### Remove a package
This uninstalls a package, completely removing everything npm installed on its behalf.
```shell
npm uninstall <module>
```

### Update packages
This command will update all the packages listed to the latest version (specified by the tag config), respecting the semver constraints of both your package and its dependencies (if they also require the same package)
```shell
npm update 
```

### Display npm bin folder
Print the folder where npm will install executables
```shell
npm bin
```

### List installed packages
This command will print to stdout all the versions of packages that are installed, as well as their dependencies when *--all* is specified, in a tree structure
```shell
npm ls
```

### Remove extraneous packages
This command removes "extraneous" packages. If a package name is provided, then only packages matching one of the supplied names are removed
```shell
npm prune
```
