Instructions:

1. Double-click on "Backup.bat" to backup the configuration and torrents of transmission to the "Backup" folder in the current directory. If there is an existing old backup, it will be renamed to "Backup.old". Older backups will be deleted, so the script will retain a maximum of two backup sets.

2. Double-click on "Restore.bat". If a backup exists in the "Backup" folder, it will be restored from there. Otherwise, it will check if there is a backup in the "Backup.old" folder, and if found, it will restore from there. If neither backup is available, it will display a message stating that no backup is available and exit.

3. The main difference from the original version is that all instances of "xcopy" have been replaced with the "RoboCopy" command. Personal testing has shown that the "RoboCopy" command is more stable.

Please note that the translation provided above is for the instructions and explanations provided in the text. The actual commands and code within the script remain the same.

===

Дважды щелкните на "Backup.bat" для резервного копирования конфигурации и торрентов  в папку "Backup" в текущем каталоге. Если существует старая резервная копия, она будет переименована в "Backup.old". Более старые резервные копии будут удалены, поэтому скрипт сохранит максимум два набора резервных копий.

Дважды щелкните на файле "Restore.bat". Если резервная копия существует в папке "Backup", она будет восстановлена оттуда. В противном случае будет проверено, есть ли резервная копия в папке "Backup.old", и если она найдена, то будет восстановлена оттуда. Если ни одна из резервных копий недоступна, программа выдаст сообщение об отсутствии резервной копии и завершит работу.

Основное отличие от оригинальной версии заключается в том, что все команды "xcopy" были заменены командой "RoboCopy". Личное тестирование показало, что команда "RoboCopy" более стабильна.

Пожалуйста, обратите внимание, что приведенный выше перевод относится к инструкциям и пояснениям, представленным в тексте. Фактические команды и код скрипта остаются неизменными.

Переведено с помощью www.DeepL.com/Translator (бесплатная версия)
