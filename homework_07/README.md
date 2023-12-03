# Homework: Module 7 - Creation and installation of custom packages

## Task

In this homework, it's required to make a folder parsing script into a Python package and a console script that can be called anywhere on the system from the console with the clean-folder command. To do this, you need to create a file and folder structure:

├── clean_folder
│    ├── clean_folder
│    │   ├── clean.py
│    │   └── __init__.py
│    └── setup.py

In clean_folder/clean_folder/clean.py it's needed to put everything we did in the previous folder parsing homework. Your main task is to write clean_folder/setup.py so that the built-in Python toolkit can install this package and the operating system can use this package as a console command.

## Task acceptance criteria

* The package is installed on the system with the 'pip install -e ' command. (or python setup.py install, requires admin rights).
* After installation, the 'clean_folder' package appears in the system.
* Once the package is installed on the system, the script can be called anywhere from the console with the 'clean-folder' command.
* A console script handles command-line arguments exactly like a Python script.
