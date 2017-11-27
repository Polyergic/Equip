# Path Conventions

When Equip installs a package directly, it will write to a limited set of paths.  Packages should follow the same convention.  (Paths below are not final.)

- `~/bin` - executable commands

- `~/bin/$platform` - platform-specific executable commands

- `~/lib` - library code used by commands in ~/bin

- `~/lib/$name/$version/data` - static data used by the $name library

- `~/etc/$name` - configurations

- `~/var/$name` - persistent state information (usually not safe to delete)

- `~/tmp` - transient state information (automatically deleted at reboot)

- `~/cache/$name` - cached data (safe to delete when program is not running)

- `~/hosts/$HOSTNAME/$above` - host-specific variants of above

Files in `tmp`, `cache`, and `hosts` are assumed to be host specific.  It is assumed to be unhelpful to sync `tmp` and `cache` across mltiple hosts; all other files are assumed to be safe (and possibly helpful) to sync between hosts.

**Note contrast with other implementations**

- XDG Desktop pathes
 
  https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html#basics
   
  - Single hidden dir is better than hidden dir per tool

  - Does not separate config from state

  - No mechanism for multiple hosts

# Types of functionality

- Commands as Executable files
- Commands as Aliases
- Commands as Bash Functions
- Library dependencies of commands
- Environment
- Session start actions
- Session end actions
- Scheduled actions

# Equip's Own Files

## Configuration

`~/etc/equip/repos.json`: JSON array of repo URLs

## Cache

`~/etc/equip/$repoURL/$name`

repo_URL is reversibly sanitized

# File Formats

## Configuration

`~/etc/equip/repos.json`

Contains JSON array of repo URLs

## Repository entry

`$reporoot/$name/$timestamp/equip.json`

JSON object with the following properties

- `equip` -- repo entry spec version
- `name` -- name of this package
- `timestamp` -- timestamp of this revision of this package
- `external` -- describes packages to install with an external package manager (e.g. the system package manager, npm, etc)
- `commands` -- describes commands provided (available in the shell environment, for users and other packages)
  - the files `~/bin/$name` or `~/bin/$platform/$name`, or alias `$name`, or function `$name`
  - the files `~/bin/$name-$subname` and/or `~/bin/$platform/$name-$subname`, and/or aliases `$name-$subname`, and/or functions `$name-$subname`
- `libs` -- describes libraries provided (available as files only, for develpers and other packages)
  - files in the directory `~/lib/$name` and/or directories `~/bin/$platform/$name`
- `config` -- describes the initial configuration, stored in directory `~/etc/$name`
- `events` -- describes events provided by this package that can be handled by other packages
  - directories named `~/etc/$name/$event`
- `handlers` -- describes handlers for events provided by other packages
  - files in directories `~/etc/$othername/$event/$name`
- `deps` -- lists packages without which this package will not work

These can be provided by events:
- path additions
- bash aliases
- bash functions
- environment variables
- login/logout actions
- scheduled tasks

# Future stuff

- automated repository creation/maintenence
  - so I can hack in my own `~/bin` and publish changes with one or two commands
  - automated version incrementing? YYYY.MM.DD.count?

- portable dependency bundles (similar to [npm](https://www.npmjs.com/)/[yarn](https://yarnpkg.com/) or [bundler](http://bundler.io/))
  - so I can update the helpers used by Equip's bootstrap 

- bootstrap script needs to accept a parameter for a virtual package to install (including repository)
  - so complete configurations can be distributed by a single command with appropriate parameters

- Allow multiple simultanious versions (with command selection)

- Install via npm/etc?

- Uninstall?  (Not uninstall a package, but uninstall Equip)

- Windows bootstrap script that does not require cygwin to be preinstalled

- Allow configuration of paths used?

