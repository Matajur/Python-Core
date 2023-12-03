# Homework: Module 8 - Features of main built-in Python packages

## Task

It's required to implement a useful function to display a list of colleagues who need to be congratulated on their birthdays for the week.
There is a list of 'users' dictionaries, each dictionary in it must have the keys 'name' and 'birthday'. This structure represents a model of a list of users with their names and birthdays. 'name' is a string with the user's name, and 'birthday' is a datetime object that contains the birthday.
The task is to write the 'get_birthdays_per_week' function, which receives a list of users as input and outputs to the console (using print) a list of users who need to be congratulated by day.

## Task acceptance criteria

* get_birthdays_per_week displays birthday people in the format:
Monday: Bill, Jill
Friday: Kim, Jan

* Users whose birthday was on the weekend should be congratulated on Monday.
* For debugging, it is convenient to create a test list of users and fill it yourself.
* The function displays users with birthdays one week ahead of the current day.
* The week starts on Monday.
