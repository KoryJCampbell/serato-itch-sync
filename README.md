# serato-itch-sync

Map one-to-one your directory structure to Serato parent crates and subcrates (also works with Scratch Live).

Latest version [0.1.5](https://github.com/sero53/serato-itch-sync/tree/master/distr/0.1.5) tested with Serato DJ Pro 2.1.0

Original see: [https://github.com/ralekseenkov/serato-sync-old](https://github.com/ralekseenkov/serato-sync-old/)
by Roman Alekseenkov

License: [GNU GPL v3](http://www.gnu.org/licenses/gpl.html)

# How do I run it ?
The installation process is very simple and it consists of two steps.

First of all, you download the latest version and put it into any directory/folder on your computer. Let's say "~/serato-itch-sync" on Mac OS, or "C:\serato-itch-sync" on Windows.

Second, you need to create the file with settings called "itch-sync.properties" in the same directory with the following contents (of course, replacing the paths to your libraries).

# Mac OS
For Mac OS, the properties file should look like: ```

# mode - gui vs. cmd
mode=gui

# path to your personal music collection
music.library.filesystem=/Users/ralekseenkov/Music/iTunes/iTunes Music/Music

# path to your serato library
music.library.itch=/Users/ralekseenkov/Music/Serato ```

Important notes for Mac OS users: * make sure to use forward slash in the library paths * the easiest way to create a properties file is to open a "TextEdit", go to "Format" menu and select "Make Plain Text", then enter the contents, and finally "File" and "Save As" giving it "itch-sync.properties" name.

# Windows
For Windows, the properties file should look like (alternatively, you can replace double backslash \\ with a single forward slash /): ```

# mode - gui vs. cmd
mode=gui

# path to your personal music collection
music.library.filesystem=C:\Music

# path to your serato library
music.library.itch=C:\Documents and Settings\ralekseenkov\My Documents\My Music\_Serato_ ```

Important notes for Windows users: * make sure to use double backslash in the library paths * the easiest way to create a properties file is to open "Notepad", enter the contents, and then "File" and "Save As" giving it "itch-sync.properties" name. Make sure you saving the file as type "All﻿ Files", so that "Notepad" doesn't add ".txt" extension to the file name

# Graphical vs. Command-Line execution mode
As you can see, there is an extra parameter in the config file, which controls the execution mode. If you are not an experienced user, it is recommended to keep the value set to "gui" (GUI means graphical user interface). If you have no issues with the command line, you can change the setting to "cmd" avoiding popup windows on your screen and achieving full automation. If GUI can not be initialized for some reason, the tool will fallback to the command-line mode automatically.

So, it's all set, and now you just need to execute the tool. In both Mac OS and Windows you can just double click the icon and it will launch the jar file (Mac OS will run jar laucher, while Windows will run java.exe or javaw.exe). Or, alternatively, you can just type "java -jar itch-sync-<version>.jar" in the command line inside the directory where the tool is installed.

# Optional settings
# Clear Serato library prior to sync
The option is useful if you want to completely Serato database before sync, erasing all previously existing crates and tracks from it, and then make a full sync with a folder on your filesystem.

By default it is disabled, so the sync preserves all existing crates and subcrates in Serato.

When enabled, it deletes all files from directories "Crates" and "Subcrates" (that clears up all existing crates in Serato), and it also deletes the file "database V2" (that clears up all existing tracks from "All" view in Serato) before the sync.

To enable, add the following lines to your properties file: ```

# deletes all existing crates from serato library prior to sync, as well as all tracks from "All" view
music.library.itch.clear-before-sync=true ```
