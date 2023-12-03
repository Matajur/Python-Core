# Combined Homework of Modules 9-12


# Homework: Module 9 - Functions (decorators, closures)

## Task

Write an assistant console bot that will recognize commands entered from the keyboard and respond accordingly.

The assistant bot should become a prototype of an assistant application for us. In the first approximation, the assistant application should be able to work with the contact book and calendar. In this homework, the focus is on the interface of the bot itself. The simplest and most convenient interface at the initial stage of development is the CLI (Command Line Interface) console application. The CLI is simple enough to implement. Any CLI consists of three main elements:

* Command parser. The part responsible for parsing strings entered by the user, extracting keywords and command modifiers from the string.
* Functions command handlers — a set of functions, also called handlers, they are responsible for the direct execution of commands.
* Request-response cycle. This part of the application is responsible for receiving data from the user and returning the response from the handler function to the user.

At the first stage, our bot-assistant must be able to save a name and a phone number, find a phone number by name, change the recorded phone number, display all the saved records in the console. To implement such simple logic, let's use a dictionary. In the dictionary, we will store the username as the key and the phone number as the value.

## Task acceptance criteria

* The bot should be in an infinite loop waiting for a user command.
* The bot completes its work if it meets the words: "good bye", "close", "exit".
* The bot is not case sensitive.
* The bot accepts commands:

 - "hello", replies to the console "How can I help you?"
 - "add ...". With this command, the bot saves a new contact in memory (in the dictionary, for example). Instead of ... the user enters the name and phone number, necessarily with a space.
 - "change ...". With this command, the bot stores the new phone number of the existing contact in memory. Instead of ... the user enters the name and phone number, necessarily with a space.
 - "phone ...". With this command, the bot outputs the phone number for the specified contact to the console. Instead of ... the user enters the name of the contact whose number should be displayed.
 - "show all". With this command, the bot outputs all saved contacts with phone numbers to the console.
 - "good bye", "close", "exit" for any of these commands, the bot ends its work after outputting "Good bye!" to the console.

* All user input errors should be handled using the input_error decorator. This decorator is responsible for returning messages like "Enter user name", "Give me name and phone please" etc. to the user. The input_error decorator should handle exceptions that occur in handler functions (KeyError, ValueError, IndexError) and return the appropriate response to the user.
* Command logic is implemented in separate functions, and these functions accept one or more lines as input and return a line.
* All the logic of interaction with the user is implemented in the main function, all print and input occur only there.


# Homework: Module 10 - Basics of working with classes

## Task

In this homework, it's required to continue development of the virtual assistant with a CLI interface.

the assistant already knows how to interact with the user using the command line, receiving commands and arguments, and performing the necessary actions. In this task, you will need to work on the internal logic of the assistant, on how data is stored, what data it is and what can be done with it.

It's needed to use object-oriented programming for these purposes. First, select several entities (models) with which to work.

The user will have an address book or a contact book. This contact book contains entries. Each record contains some set of fields.

In this way, the entities (classes) were described that need to be implemented. Next, consider the requirements for these classes and establish their relationship, the rules by which they will interact.

The user interacts with the contact book by adding, deleting and editing entries. Also, the user should be able to search for entries in the contact book by one or more criteria (fields).

It's also possible to say about the fields that they can be mandatory (name) and optional (phone or email, for example). Additionally, records can contain several fields of the same type (several phones, for example). User should be able to add/delete/edit fields in any record.

In this homework, the following classes to be implemented:

* An AddressBook class that inherits from UserDict, and we'll then add the record search logic to this class.
* The Record class, which is responsible for the logic of adding/removing/editing optional fields and storing the mandatory Name field.
* The Field class, which will be the parent for all fields, will then implement the logic common to all fields in it.
* Name class, mandatory name field.
* The Phone class, an optional field with a phone number, and so on, one record (Record) can contain several.

## Task acceptance criteria

* All classes from the task have been implemented.
* Record entries in AddressBook are stored as values in a dictionary. Record.name.value is used as keys.
* Record stores the Name object in a separate attribute.
* Record stores a list of Phone objects in a separate attribute.
* Record implements methods for adding/removing/editing Phone objects.
* AddressBook implements the add_record method, which adds a Record to self.data.


# Homework: Module 11 - Magic methods

## Task

In this homework it's needed to:

* Add a Birthday field. This field is optional, but there can be only one.
* Add the functionality of working with Birthday to the Record class, namely the days_to_birthday function, which returns the number of days until the next birthday.
* Add a functionality to check the correctness of the given values for the Phone, Birthday fields.
* Add pagination (page-by-page output) for AddressBook for situations when the book is very large and you need to show the content in parts, and not all at once. We implement this by creating an iterator by records.

## Task acceptance criteria

* AddressBook implements an iterator method that returns a generator over AddressBook entries and returns a representation for N entries in one iteration.
* The Record class accepts one additional (optional) argument of the Birthday class.
* The Record class implements the days_to_birthday method, which returns the number of days until the contact's next birthday if the birthday is given.
* setter and getter logic for the value attributes of the Field inheritors.
* Checking the correctness of the entered phone number setter for the value of the Phone class.
* Checking the correctness of the entered birthday setter for the value of the Birthday class.


# Homework: Module 12 - Serialization and copying of objects

## Task

In this homework it's needed to:

* Add the functionality of saving the address book to disk and restoring it from disk. To do this, you can choose any data serialization/deserialization protocol that is convenient for you and implement methods that will save all data to a file and load it from a file.
* Add the ability to search the contents of the contact book to the user, so that all information about one or more users can be found by a few digits of the phone number or letters of the name, etc.

## Task acceptance criteria

* The application does not lose data after exiting the application and restores it from a file.
* The application displays a list of users whose name or phone number matches the entered string.
