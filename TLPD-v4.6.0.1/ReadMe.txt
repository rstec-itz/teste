
TLPD (Too Long Path Detector)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
by Or Ben Shabat


Brief
~~~~~~
TLPD scans the directory tree, looking for files and folders with full
path name longer than a specified threshold. the reason for this is the
inability of Windows operating systems to handle path names longer than
255 characters. some programs fail to work correctly with them, and TLPD
is used to detect them for you, so you can move or rename them to shorter
paths.


Standard Use
~~~~~~~~~~~~~
you can start TLPD in the usual way, and then you are asked for the path to
check and for the threshold to use. with these parameters the program gets
to work (this may take a minute or two), and displays a log with a list of
files and folders with too long path names.

the log is saved in your temporary folder (%TEMP%) by the name "TLPD-log.txt"
for later review.


Advanced Use
~~~~~~~~~~~~~
you can start TLPD with command-line parameters, the 1st is the path to check,
and the 2nd is the threshold.
for example:	tlpd.exe c: 200

this is intended for automated silent operation. this means that the log file
is not presented to the user, only saved to disk. you can integrate TLPD into
a script in this way, and make use of the exit codes described hereunder.

you may also pass asterisk (*) as the first parameter (instead of a specific
path), and TLPD will scan all drives (local and network) in your system.
for example:	tlpd.exe * 200

if the command-line parameters are misconfigured, the program exits with the
relevant exit code (see hereunder).


Tray Icon
~~~~~~~~~~
TLPD displays a tray icon, indicating that the program is in progress.
use the tray icon menu to suspend, resume or exit the program.
"Running" and "Suspended" states display different icons and tooltip.

in silent mode, the tray icon is not displayed. however, you can see that it
is in progress by the TLPD process (TLPD.exe or TLPD_x64.exe) in the Windows
Task Manager, and also terminate it from there.


Exit Codes
~~~~~~~~~~~
TLPD returns the following exit codes:
0 - program completed successfully, too long paths were not found
1 - program terminated by external means
2 - error in path parameter
3 - error in threshold parameter
4 - error in parameters count
5 - reserved
6 - reserved
7 - reserved
8 - program completed successfully, too long paths were found!
9 - aborted by the user


Open Source
~~~~~~~~~~~~
TLPD is an Autoit v3.3.14.5 script.
source files and compiled executables (32-bit and 64-bit) are available.

TLPD was developed as a complementary product for the EVACopy project:
http://evacopy.sourceforge.net
however, it is very useful as a standalone program as well.


enjoy!
