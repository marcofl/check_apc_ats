#Check APC ATS

This is a basic icinga plugin to monitor the status of Schneider Electric / APC Automatic Transfer Switches
written in ruby (works with ruby 1.8.7 and snmp-gem 1.2 or later)

###Installation
snmp gem has to be installed
```
gem install snmp
```
### Usage

```
./check_apc_ats -H 1.2.3.4 -C public
Check ATS: State OK
```
as an icinga check command:
```
define command{
        command_name    check_apc_ats
        command_line    $USER1$/check_apc_ats -H $HOSTADDRESS$ -C $ARG1$
        }
```
for old ruby 1.8.x (like on CentOS 6) use this command, so gems require work:
```
        command_line /usr/bin/ruby -rubygems $USER1$/check_apc_ats -H $HOSTADDRESS$ -C $ARG1$
```

##LICENSE
This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
