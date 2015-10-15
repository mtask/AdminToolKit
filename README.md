Atk is toolkit for Linux sysadmins or for home users with Linux machines. It has it's own shell-like enviroment which prompt supports tab autocompletion and command history with up arrow(only current session).

###Depencies

$ pip install IPy

$ pip install fabric

## Run atk's "shell"

&gt; python atk.py

##Atk's Commands

###- multissh

Remotely run commands on multiple ssh servers.

Basic usage: &gt; multissh [command]

Run local script on host(s): &gt; multissh -script [script_name]

Run local script with sudo: &gt; multissh -script sudo [script_name]

Copy file from host(s): &gt;multissh -copy [remotepath] [localpath]

Copy file to host(s):&gt;multissh -put [localpath] [remotepath]

Modify multissh.conf file in atk's directory with the following form with one host+user per line:"[user@host]=[user]" (without quotes).
Multissh can ofcourse be used also to run remote commands in one server only. Hosts can be commented out with "#", so certain hosts can be skipped without removing them. When running local scripts the script is copied to host and then executed.

###- keyparser

Usage: &gt; keyparser --path [authorized_keys_file_path]

Parse keys and options from authorized_keys file to SQLite database.

Default path to authorized_keys is set to "~/.ssh/". Custom path can be set with "--path [PATH]" argument.

Structure of auth_keys.db:

+----+---------------+--------------+

| id |      key      | option names |

+----+---------------+--------------+

|  1 | ssh-rsa AA... | options      |

+----+---------------+--------------+

###- netmon

Usage: &gt; netmon [time]  [interval]

time - Monitoring time

interval - Connection status checking interval.

With netmon command you can start internet connection status monitoring in background. Monitoring lasts for given time and internet connection is checked for given interval. It logs connection's down times and if connection has been restored. Monitorin and interval time is given in minutes. Monitoring will be finished even if user exits from atk's shell.

###- harvest

Usage: &gt; harvest  [file] -s

file - Path to file where to harvest addresses
-s - Save finds to file(optional)

With harvest command you can find IP and MAC addresses from given file. It prints findings to screen but you can also save results to file. Saved files are atm. stored in atk's directory.

###- lookup
Simple dns lookup.

Usage: &gt; lookup [address/domain]

###- quick_share

Quickly share files under given path. WARNING: With quick_share no authentication is needed to access shared files.

Usage: &gt; quick_share [path] [port]


###- Other commands

help - Print help page. Add command name after help to get more info

clear - Clear screen

ls - List files

pwd - Get cwd path

exit - Exit
