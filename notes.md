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

`$name-$timestamp.json`

JSON object with the following properties

- `cmd` -- describes the file `~/bin/$name`, and/or files `~/bin/$platform/$name`, and/or `~/bin/$name-$subname`
- `lib` -- describes the directory `~/lib/$name` and/or directories `~/bin/$platform/$name`
- `cfg` -- describes the directory `~/etc/$name` and/or files in directories `~/etc/$othername/$hook/$name`
- `native` -- describes packages to install with the system package manager
- `deps` -- equipment without which this piece will not work

These can be provided by hooks:
- path additions
- bash aliases
- bash functions
- environment variables
- login/logout actions
- scheduled tasks

# Future stuff

- bootstrap script needs to accept a parameter for a virtual package to install (including repository)
  - so complete configurations can be distributed by a single command with appropriate parameters

- Allow multiple simultanious versions (with command selection)

- Windows bootstrap script that does not require cygwin to be preinstalled

- Allow configuration of paths used?

