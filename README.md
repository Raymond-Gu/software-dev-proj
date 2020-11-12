# software-dev-proj
ICS4U Culminating project - Nov 2020




## Engine Physics Controller


The Engine Physics Controller is a program designed for game developers with their engine-based game in mind. This program is meant to simplify and facilitiate the creation and usage of physics for those engines. The laws of physics for a game's engine can be stored inside a single dedicated directory within the engine's files, making it much easier to view and access them as a developer, while still allowing easy access from the rest of the engine.



## How it works / Overview


The Engine Physics Controller can best be described as "a game that makes other games." The program is made up of two parts, both accessible by the developer: a custom-built engine designed specifically for simulation with the flexibility of physics rules in mind, and a refined UI to allow usage by any developer of any skill level. The UI consists of various sections containing object classes and groups, active physics laws, an interactive menu to alter the selected law through sliders and toggleables, and various other tools the developer will find useful for their creation process right at their fingertips. It also has a section for the simulation, in which the engine will be running and simulating the developer's created laws using our own world props and objects to allow for quick and easy testing within the program. It's built entirely on a custom variation of C called C-ration (pronounced "creation") with a focus on language conversion. This is arguably one of the most vital aspects of the Engine Physics Controller in order to allow the developer to export and use their ready-made rules and be able to implement into their own game.



## Features and Details


### Saving, Backing up, Crashing, and Logging

If the developer ever wishes to keep their progress between sessions or is simply not ready to export their work yet, they can save their progress in a custom file format. This file will have the extension `.epc`, and is a save file containing all the necessary information for the program to be able to pick up where it left off. Saving frequently is a heavily recommended practice for any developer, as the risk of possibly losing a large amount of, if not all, progress is infinitely more frustrating and time consuming than a couple button clicks. Saves should be stored in their own directory, and can be stored anywhere on the developer's computer. The program has two separate modules for automatically creating backups in a subdirectory of the save files, in the case of a save file becoming corrupted and unuseable for any reason. Backups are stored with the extension of `.epc.old`, and can be loaded as a backup from within the program. The program will recognize it as a backup and cross-reference any data with its own caches in an attempt to salvage any possibly lost data. Should any conflicting settings surface, the developer will have the choice between keeping various settings, and the program will restore as much work as possible.

In the case of a program crash, should the program be able to recognise one on its own in time, it will automatically keep a separate save, called a crash file, with the extension `.epc.crash` and will also create a crashlog file for debugging. The developer can optionally send any crash data automatically to the program's developer (me, if this existed) for future bugfixes / improvements to the program. Upon launching and loading a save file post-crash, should the save file have a crash file with a matching name, the developer will be given the option of either loading the last save, or loading from the crash. Should they choose to load from the crash, the program will cross-reference data from the save file, the crash file (should it not be a glorified, corrupt save file), and its caches, and try to salvage as much data as possible. Just like loading a backup, the developer will be given the choice between conflicting settings and will be able to resume work quickly.


### Importing and Exporting


The whole principle of the Engine Physics Controller is for the developer's custom made laws to be exported and implemented into their own game. In order for this to happen, the program requires import/export capabilities. As a variety of laws, objects, and groups are created by the developer, various files are created, altered, and removed in order to match the properties of the developer. These files are internally tracked, categorized, and labelled, so that when the developer is ready to export their rules for implementation and/or testing, they will automatically be placed in a detailed and organized directory (named `physics`, which will be compressed in a `.zip` file), ready for the developer to simply add into their game's main directory for use. Upon exporting, the developer will have a choice of languages to export in. This is because games are not all written in the same language - popular game "Minecraft" is written in Java, for example, while the old first person shooter "Quake" is written in a variation of C. The ability to export in any common language (such as C, C++, C#, Java, Python, etc.) is part of the essence of the Engine Physics Controller.

Importing previously made files is just as simple - simply locating the parent directory of the physics section (also named `physics`, the same one that was exported) and import it. The program will automatically unpack, open, and read every single file and change the settings of the UI in order to match those of the imported files. From there, the developer can easily make any necessary changes to their rules and export them, and replace the old directory in their game's files to the new, updated directory.

Sometimes, a developer will only want to make a quick, simple change to their rules. Instead of importing all the files, changing that one obscure setting and exporting all over again, they can use a function called "direct editing." What direct editing does is instead of reading every single file and importing all the settings, it simply performs a quick scan over the directory to locate all the files, after which the developer can choose what they'd like to edit, and the program will only load the necessary files. Not only does this save time and allow simple changes to be made much quicker, this can be done without importing a single file. Once given the directory, the program can directly edit those files to make the changes, instead of loading the file, creating a copy, making the changes, and *then* exporting the file which requires the previous one to be deleted anyway. Seeing as this feature edits files outside the program's own files and directories, Engine Physics Controller must be launched with system administrative privileges in order for this feature to be available.
