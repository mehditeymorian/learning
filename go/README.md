# Go CLI
<p align="center">
    <img src="../assets/go-logo.png" width="512" />
</p>

## Init Module (Project)
Init initializes and writes a new go.mod file in the current directory with the given path.
```shell
go mod init [module-path]
```

## Download Modules
Download downloads modules to local
```shell
# downloads named modules
go mod download [modules]
# downloads modules needed to build and test
go mod download
```

## Fix modules
Tidy makes sure go.mod matches the source code in the module.
It adds any missing modules necessary to build the current module's
packages and dependencies, and it removes unused modules that
don't provide any relevant packages. It also adds any missing entries
to go.sum and removes any unnecessary ones.
### Options
- `-v`: print info about removed modules to standard output.
- `-e`: force option. this flag causes tidy to attempt to proceed despite errors encountered while loading packages.
```shell
go mod tidy
```

## Verify Downloaded Dependencies
Verify checks that the dependencies of the current module,
which are stored in a local downloaded source cache, have not been
modified since being downloaded.
```shell
go mod verify
```

## Vendor
Vendor resets the main module's vendor directory to include all packages
needed to build and test all the main module's packages.
It does not include test code for vendored packages.
### Options
- `-v`: flag causes vendor to print the names of vendored modules and packages to standard error.
- `-e`: force option. flag causes vendor to attempt to proceed despite errors encountered while loading packages.
```shell
go mod vendor
```

## Build Module
compile packages and dependencies.  
`Note`:If the arguments to build are a list of .go files from a single directory,
build treats them as a list of source files specifying a single package.
### Options
- `-race`: enable data race detection.
```shell
go build [packages]
```

## Run
Run compiles and runs the named main Go package.
Typically, the package is specified as a list of .go source files from a single
directory, but it may also be an import path, file system path, or pattern    
matching a single known package, as in 'go run .' or 'go run my/cmd'.
```shell
# run single file
go run main.go
# run main package along with its dependencies
go run main.go dependency-1.go dependency-1.go ...
```