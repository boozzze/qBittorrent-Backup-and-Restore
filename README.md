Because using the .bat file extension can make some users concerned about potential malicious code in the script, the file extension of the script has been changed to .txt to minimize the risk of accidental execution. Users can review the code instructions in the script to ensure that the script does not have any malicious behavior.

Instructions:
1. Change the file extension of both "Backup.txt" and "Restore.txt" files from .txt to .bat (If your system is set to hide file extensions, please search "how to show file extensions" on the internet).

2. Double-click on "Backup.bat" to backup the configuration and torrents of transmission to the "Backup" folder in the current directory. If there is an existing old backup, it will be renamed to "Backup.old". Older backups will be deleted, so the script will retain a maximum of two backup sets.

3. Double-click on "Restore.bat". If a backup exists in the "Backup" folder, it will be restored from there. Otherwise, it will check if there is a backup in the "Backup.old" folder, and if found, it will restore from there. If neither backup is available, it will display a message stating that no backup is available and exit.

4. The main difference from the original version is that all instances of "xcopy" have been replaced with the "RoboCopy" command. Personal testing has shown that the "RoboCopy" command is more stable.

Please note that the translation provided above is for the instructions and explanations provided in the text. The actual commands and code within the script remain the same.
