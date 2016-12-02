# Shellacc

The "Shell Accoutrements" I use on all of my computers.

This is here in part to simplify replicating my setup on new computers and trmporary VMs, and in part to share the useful solutions with whoever may benefit.

## What's included

This is an eclectic set of commands, settings, and configurations that I use on my personal computers.  Most of what's included is my own creations, including many trivial helpers, and many scripts that took nontrivial work but didn't warrant publication as a separate project.  Some of what's included is copied or derived from various sources throughout the internet, and I've attempted to link to sources wherever possible.  If you find an error or omission please create an issue in this repository.

## Installation

Once implemented, you'll be able to "equip" almost any bash shell using this command:

    curl https://raw.githubusercontent.com/Polyergic/Shellacc/master/bin/equip -# -f | bash

Someday you'll be able to selectively apply the settings and configurations you want to adopt.

## Licensing

New work in this repository is licensed under [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html) (see file `LICENSE`):

> Shellacc - The "Shell Accoutrements" I use on all of my computers. <br/>
> Copyright (c) 2016 Shad Sterling
> 
> This program is free software: you can redistribute it and/or modify
> it under the terms of the GNU Affero General Public License as
> published by the Free Software Foundation, either version 3 of the
> License, or (at your option) any later version.
> 
> This program is distributed in the hope that it will be useful,
> but WITHOUT ANY WARRANTY; without even the implied warranty of
> MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
> GNU Affero General Public License for more details.
> 
> You should have received a copy of the GNU Affero General Public License
> along with this program.  If not, see <http://www.gnu.org/licenses/>.

Adopted and derived portions are used under their original license:
 - For any directory containing another `LICENSE` file, all files and subdirectories not containing yet another `LICENSE` file are licensed by the copyrightholder under the license therein.
 - For sections within files that are attributed to a source (and large enough to be subject to copyright), the section falls under the license given in the attribution or specified at the source URL.
   - Many of these are adaptations of answers on Stack Exchange sites, all of which are [licensed under](http://stackoverflow.com/help/licensing) [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)
<!---
; that license [allows derivative licensing under](https://wiki.creativecommons.org/wiki/License_Versions#Compatibility_mechanism_in_BY-SA_licenses) [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) which [allows derivative licensing under](https://creativecommons.org/share-your-work/licensing-considerations/compatible-licenses/) [GPLv3](https://www.gnu.org/licenses/gpl-3.0.en.html) which ... actually [does not allow derivative licensing] under(http://softwareengineering.stackexchange.com/questions/288292/can-i-take-a-gpl-program-and-relicense-my-changes-under-the-agpl?rq=1) [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html)
-->

Please create issues in this repository to report any errors in licensing or attribution.

## Current Status:

### MacOS

Installs [MacPorts](https://www.macports.org/)
