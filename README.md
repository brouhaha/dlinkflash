dlinkflash
2014-11-08
==========

This is Daniel Dickinson's dlinkflash program to flash firmware of
DLink DIR-825, and possibly other models.  Some minor bug fixes and
cleanup by Eric Smith.  This program may be useful for flashing
OpenWRT on a DIR-825.  No technical support is offered or provided.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or (at
your option) any later version.

This program is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU
General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>. 

Original version from OpenWRT DIR-825 wiki page:
  http://wiki.openwrt.org/toh/d-link/dir-825#a.c.program.to.flash.dir-825

This version hosted at Github:
  https://github.com/brouhaha/dlinkflash

This program is useful because the DIR-825 recovery mode's web server
is horribly broken, and only works correctly with IE6.  dlinkflash
simulates the necessary stupidity to make the DIR-825 recovery mode
work.

Note that even using dlinkflash, the DIR-825 recovery mode WILL NOT
WORK if the Ethernet port is used a 1 Gbps, despite that the DIR-825
ethernet ports are all 1 Gbps ports.  If you try, there is such a high
degree of TCP lossage that it will take more than 24 hours to transfer
the firmware; I've never run it long enough to find out whether it
will eventually succeed.  When using the Ethernet port at 100 Mbps
instead, the firmware transfer completes nearly instantly.

Reportedly you can connect directly the DIR-825 port to a Linux
machine and manually configure the Ethernet port on the Linux machine
to do 100 Mbps, but I've never gotten that to work.  Instead, I
recommend reflashing the DIR-825 with it plugged into a port of 10/100
(not 1G) Ethernet switch, in which case you don't have to do anything
special on the Linux machine (other than using dlinkflash).
