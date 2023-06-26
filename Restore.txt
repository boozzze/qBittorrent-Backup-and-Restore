@echo off
IF NOT EXIST ".\Backup" GOTO SearchBakOld
ECHO Restoring qBittorrent configuration from "Backup"
ECHO To cancel the restoration, press Ctrl+C. Otherwise, press any key to start the restoration
PAUSE > NUL
IF EXIST "%LocalAppData%\qBittorrent" (
	RD /S /Q  "%LocalAppData%\qBittorrent"
)
RoboCopy ".\Backup\Local\qBittorrent" "%LocalAppData%\qBittorrent" /E /NFL /NDL /NC /NS /NP
IF EXIST "%AppData%\qBittorrent" (
	RD /S /Q "%AppData%\qBittorrent"
)
RoboCopy ".\Backup\Roaming\qBittorrent" "%AppData%\qBittorrent" /E /NFL /NDL /NC /NS /NP
ECHO Successfully restored configuration from "Backup". Press any key to exit...
PAUSE > NUL
EXIT

:SearchBakOld
IF NOT EXIST ".\Backup.old" GOTO BakNotFound
ECHO Restoring qBittorrent configuration from "Backup.old"
ECHO To cancel the restoration, press Ctrl+C. Otherwise, press any key to start the restoration
PAUSE > NUL
IF EXIST "%LocalAppData%\qBittorrent" (
	RD /S /Q  "%LocalAppData%\qBittorrent"
)
RoboCopy ".\Backup.old\Local\qBittorrent" "%LocalAppData%\qBittorrent" /E /NFL /NDL /NJH /NJS /NC /NS /NP
IF EXIST "%AppData%\qBittorrent" (
	RD /S /Q "%AppData%\qBittorrent"
)
RoboCopy ".\Backup.old\Roaming\qBittorrent" "%AppData%\qBittorrent" /E /NFL /NDL /NJH /NJS /NC /NS /NP
ECHO Successfully restored configuration from "Backup.old". Press any key to exit...
PAUSE > NUL
EXIT

:BakNotFound
ECHO No available backup found. Restoration aborted. Press any key to exit...
PAUSE > NUL
