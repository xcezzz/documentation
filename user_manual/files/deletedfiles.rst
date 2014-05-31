Deleted Files
=============

|cloudName| keeps a copy of your deleted files in case you need them again. To
make sure that the user doesn't run out of memory, the deleted files app
manages the size of the deleted files for the user. The app takes care to never
use more that 50% of your currently available free space. If your deleted files
exceed this limit, |cloudName| deletes the oldest versions until it meets the memory
usage limit again.

Deleted files can be found by clicking on the *Deleted files* button on files app of web interface.
You can either restore or permanently delete using appropriate buttons.

|cloudName| also checks the age of deleted files every time new files are added
to the deleted files. By default, deleted files stay in the trash bin for 180 days.
Additionally, |cloudName| calculates the maximum available space every time
a new file is added. If the deleted files exceed the new maximum allowed space
|cloudName| will expire old deleted files until the limit is met once again.
