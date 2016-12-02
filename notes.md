# Mac

- Detect MacOS:

  Use `platform` script from within project;

  Download key scripts into `~/tmp/shellac-equip-bootstrap`

- Enable developer tools:

  `sudo xcodebuild -license accept`
  
  found on https://stackoverflow.com/questions/26197347/26772631#comment53485674_26772631

- Install MacPorts from within Terminal:

  Source: https://excitedcuriosity.wordpress.com/2007/08/17/installing-macports-from-the-command-line/

  > `curl -O http://svn.macports.org/repository/macports/downloads/MacPorts-1.5.0/MacPorts-1.5.0-10.4.dmg`

  > `hdiutil attach MacPorts-1.5.0-10.4.dmg`

  > `sudo installer -verbose -pkg /Volumes/MacPorts-1.5.0/MacPorts-1.5.0.pkg -target /`

  > `sudo port -v selfupdate`

  > `hdiutil detach -verbose /dev/disk4`

  Changes needed:
  - query to find current version (for URL and pkg name)
  - detect mountpoint when mounting image & unmount accordingly 

# Paths
A weak suggestion for an FHS-like allocation of paths in $HOME

- `~/bin` - executable commands

- `~/lib` - library code used by commands in ~/bin

- `~/lib/$name/data` - static data used by the $name library

- `~/etc` - configurations

- `~/var` - persistent state information (not necessarily safe to delete)

- `~/tmp` - transient state information (safe to delete)

- `~/hosts/$HOSTNAME/$above` - host-specific variants of above

**Note contrast with other implementations**

- XDG Desktop pathes
 
  https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html#basics
   
  - Single hidden dir is better than hidden dir per tool

  - Does not separate config from state

  - No mechanism for multiple hosts
