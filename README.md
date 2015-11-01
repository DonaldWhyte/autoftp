![AutoFTP](https://github.com/DonaldWhyte/autoftp/raw/wiki/autoftp_logo.png)

AutoFTP synchronises a directory on your local machine to a server using FTP.
This eliminates the need to manually transfer files to and from a server using
an FTP client, as it's all done in the background. In addition to being used
for website developers, it can act as a backup tool for important data. Simply
keep AutoFTP running in your taskbar and it will periodically merge the local
directory and the server, keeping both up-to-date in a similar fashion to
version control.

### Build

Build all the source files in the `autoftp` package to a JAR file (e.g. `autoftp.jar`). Be sure that you add the directory(s) which contain the dependencies list below to the classpath.

Dependencies:

* [commons-net](https://commons.apache.org/proper/commons-net/)

### Installation

Ensure that you have the latest version of Java. Other than that, no
installation is required. Simply run `autoftp.jar` to run the program.
Ensure that `icon.png`, `settings.conf` and `text_extensions.conf` are in the same folder as JAR file being executed.

### Usage

In order for AutoFTP to work, you must provide it with some information first. After opening the program, right-click on its tray icon and select 'Options'. Here you need to enter the path to the local directory and the address of the server you want to sync. Bear in mind you may also need special permission to modify files on the server, so a username and password can be entered too. It is also possible to change the amount of time between merges. The recommended merge frequency is 10-30 seconds, but if your server has a large amount of data and/or new files being added/removed frequently, then a longer time between merges may be appropriate to prevent taxing your local machine or server.

After entering your settings, AutoFTP will start merging the local directory's and server's files. To stop this process, you can either pause AutoFTP by selecting 'Pause' on the tray icon menu, or just exit the program (bear in mind it may take a while to exit if the program is currently merging, as it needs to finish).

AutoFTP detects whenever new files/directories have been added to the program and whether files have been updated and then merges these changes. However, it does not automatically detect a file being removed. This is because it cannot determine if a file has been removed or if it wasn't in the local directory/server, so it can't decide whether it needs to send the file to the directory without it or remove it from the one that has it.

Instead, you can remove files by clicking on the 'Remove Files' option in the tray icon menu. A window showing all the files in the local directory and server will appear, allowing you to select files and remove them. Doing so will remove the file from both the local directory and server, so it won't be a problem when the next merge starts.
