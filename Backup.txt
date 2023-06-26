@echo off
IF NOT EXIST "%LocalAppData%\qBittorrent" GOTO CfgNotFound
IF NOT EXIST "%AppData%\qBittorrent" GOTO CfgNotFound
ECHO Backing up the relevant configuration files of qBittorrent to "Backup"
ECHO To cancel the backup, press Ctrl+C. Otherwise, press any key to start the backup
PAUSE > NUL
IF EXIST ".\Backup" (
	IF EXIST ".\Backup.old" (
		RD /S /Q ".\Backup.old"
	)
	MOVE ".\Backup" ".\Backup.old"
	ECHO The previous backup has been renamed to "Backup.old"
)
RoboCopy "%LocalAppData%\qBittorrent" ".\Backup\Local\qBittorrent" /E /NFL /NDL /NC /NS /NP
RoboCopy "%AppData%\qBittorrent" ".\Backup\Roaming\qBittorrent" /E /NFL /NDL /NC /NS /NP
ECHO Backup completed. Press any key to exit...
PAUSE > NUL
EXIT

:CfgNotFound
ECHO The qBittorrent configuration files were not found. Unable to perform backup. Press any key to exit...
PAUSE > NUL
