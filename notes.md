# Mac

- Detect MacOS:

  Use `platform` script from within project;

  Download key scripts into `~/tmp/shellac-equip-bootstrap`


- Install MacPorts from within Terminal:

  Source: https://excitedcuriosity.wordpress.com/2007/08/17/installing-macports-from-the-command-line/

  > curl -O http://svn.macports.org/repository/macports/downloads/MacPorts-1.5.0/MacPorts-1.5.0-10.4.dmg

  > hdiutil attach MacPorts-1.5.0-10.4.dmg

  > sudo installer -verbose -pkg /Volumes/MacPorts-1.5.0/MacPorts-1.5.0.pkg -target /

  > sudo port -v selfupdate

  > hdiutil detach -verbose /dev/disk4

  Changes needed:
  - query to find current version (for URL and pkg name)
  - detect mountpoint when mounting image & unmount accordingly 
