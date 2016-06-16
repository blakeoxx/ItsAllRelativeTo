# Application Objectives
This document lays out the core features and flow the application must contain in order to be considered finished.

## Views
For our purposes here, a view is defined as a user interface presented either as a standalone page, a pop-in, or a page load-over. Which of these is appropriate for each view is beyond the scope of this document.

### Home View
- Must contain a text box for the "object from"
- Must contain a text box for the “object to”
- Must contain a submit button

### Object Definition View
- Must display the message: “[OBJECT NAME] isn’t in our database. Help us out”
- Must contain a text box for the “object name”
- Must contain a text box for the “object plural”
- Must contain a method of providing a list of object aliases
- Must contain a method of providing sizing information using a list of pre-defined units of measure
- Must contain a method of providing a source/citation for sizing information
- Must contain a submit button
- Must contain a cancel button

### Comparison View
- Must display the “object from” name
- Must display the “object to” name
- Must display how many “object to”’s comprise “object from”
- Must contain a method of changing names, aliases, sizing information, and sources/citations for either object
- Must contain a method of starting a new comparison

## Features

### Object Comparison
- When a new comparison is started from the Home or Comparison View with a single object, the database should be queried for the object
  - If the object is found in the database, the Comparison View should show the object plus a random smaller object and calculated “how many” value
  - If the object is not found in the database, the Object Definition View should be shown
- When a new comparison is started from the Home or Comparison View with two objects, the database should be queried for the objects
  - If both objects are found in the database, the Comparison View should show the objects and calculated “how many” value
  - If one or both objects are not found in the database, the Object Definition View should be shown

### Object Definition
- An Object Definition must have a name, plural, and at least one piece of sizing information
- Each piece of sizing information for an Object Definition must have a source/citation
- When an Object Definition is submitted from the Object Definition View, the database should be queried for the object name, plural, and aliases
  - If an object is found in the database matching any of the values, an error should be thrown
  - If all values are unique in the database, the object should be saved
    - If the Object Definition was the result of an Object Comparison, the comparison should continue as normal
    - If the Object Definition was the result of a change to an existing object, the Object Comparison View should be refreshed with the updated information
