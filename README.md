# Equip

Tool to equip your shell with the things you need.

This is a sort of package manager, the packages for which can specify to install files under your `$HOME` or to use the system package manager to install system packages.  System packages will be installed when privleges are available, otherwise instructions will be generated which a privledged user can follow to install them.

Equip is intended to be compatible with a `$HOME` which is synchronized across several computers (e.g. with [Unison](https://www.cis.upenn.edu/~bcpierce/unison/)) not necessarily running the same host OS.

This is a spinoff of my effort to simplify replicating my setup on new computers and temporary VMs, as well as to share the useful solutions with whomever may benefit.  It separates the mechanisms used for replication from the tools and configurations to be replicated.

## Supported Systems

Because packages may include information about installing system packages, it is possible for a repository to not support for some systems which are supported by Equip itself, or for a package to represent functionality which is not available on some systems which are otherwise supported.  It is not possible to provide a universal solution to this problem, so even supported systems may not always behave as expected.

Primary development is done on MacOS, where [MacPorts](https://www.macports.org/) is used as a system package manager.  Support of MacOS is beginning to be implemented.

Testing will be done on at least OpenSUSE and CentOS, and maybe be done on other Linux distributions.  Support of Linux distributions is currently nonexistent, is planned for at least 2 distributions, and may be expanded.

Testing will be done on Windows with Cygwin

## Installation

Once implemented, you'll be able to "equip" a shell on MacOS, some Linuxes, and Cygwin with this command:

    curl -f -# https://raw.githubusercontent.com/Polyergic/Equip/master/bin/equip-bootstrap | bash

This will install all necessary system packages (or give instructions for doing so if privleges are not available), and do some rearranging of your shell configuration files to make them modular and ensure that installed tools are in your path.  On MacOS this will install MacPorts, and use it to install some of the necessary "system" packages (or give instructions for doing so if privleges are not available).

## Licensing

New work in this repository is licensed under [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html) (see file `LICENSE`):

> Equip - Tool to equip your shell with the things you need. <br/>
> Copyright (c) 2017 Shad Sterling
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
