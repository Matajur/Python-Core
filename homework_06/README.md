# Homework: Module 6 - Operations with files

## Task

Many people have a folder on their desktop called something like "To sort". As a rule, hands never manage to disassemble this folder.
It's required to write a script that will analyze this folder. Ultimately, you can customize this program for you and it will run a custom script that suits your needs. To do this, our application will check the file extension (the last characters in the file name, usually after a dot) and, depending on the extension, decide to which category to assign this file.
The script takes one argument at startup — the name of the folder in which it will sort. Suppose the file with the program is called sort.py, then to sort the folder /user/Desktop/Junk, you need to run the script with the command python sort.py /user/Desktop/Junk

* In order to successfully cope with this task, you must transfer the folder processing logic to a separate function.
* In order for the script to be able to traverse any depth of nesting, the folder handling function must recursively call itself when it encounters nested folders.

### The script should go through the folder specified during the call and sort all files by groups:

* images ('JPEG', 'PNG', 'JPG', 'SVG');
* video files ('AVI', 'MP4', 'MOV', 'MKV');
* documents ('DOC', 'DOCX', 'TXT', 'PDF', 'XLSX', 'PPTX');
* music ('MP3', 'OGG', 'WAV', 'AMR');
* archives ('ZIP', 'GZ', 'TAR');
* unknown extensions.

### The results of the work should include:

* List of files in each category (music, video, photo, etc.)
* A list of all known script extensions found in the target folder.
* A list of all extensions unknown to the script.

Then you need to add functions that will be responsible for processing each type of file.
Also, all files and folders must be renamed by removing any problematic characters from the name. To do this, you need to apply the normalize function to file names. It is worth understanding that you need to rename the files so that the file extensions are not changed.

### Function 'normalize':

* Transliterates the Cyrillic alphabet into Latin.
* Replaces all characters except Latin letters and numbers with '_'.

### Requirements for the function 'normalize':

* takes a string as input and returns a string;
* transliterates Cyrillic characters into Latin;
* replaces all characters except Latin letters and numbers with the character '_';
* the transliteration may not conform to the standard but be readable;
* uppercase letters remain uppercase and lowercase remain lowercase after transliteration.

### Conditions for processing:

* transfer the image to the 'images' folder;
* transfer the documents to the 'documents' folder;
* audio files are transferred to 'audio';
* video files to 'video';
* the archives are unpacked and their contents are transferred to the 'archives' folder.

## Task acceptance criteria

* all files and folders are renamed using the 'normalize' function;
* file extensions do not change after renaming;
* empty folders are deleted;
* the script ignores 'archives', 'video', 'audio', 'documents', 'images' folders;
* the unpacked contents of the archive are transferred to the 'archives' folder in a subfolder named the same as the archive, but without the extension at the end;
* files whose extensions are unknown remain unchanged.
