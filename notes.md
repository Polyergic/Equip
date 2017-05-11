# Paths

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

