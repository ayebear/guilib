Guilib
======

This is a very simple to use GUI library. It is written in C++11 and uses SFML. It is meant to be used in programs that already use SFML but need a GUI.

You can define your GUI layout and style in two configuration files.

GUI elements
------------

You will be able to create your own GUI elements, and there will be a basic set of GUI elements provided with the library.

* BaseElement
  * Would have a set of properties that could be set by sub classes.
    * Sticky/non-sticky
    * Clickable
    * And many more...
  * This would also have all of the basic methods that GUI elements should have, like:
    * handleEvent(), update(), draw(), etc.
* Label
  * A single line of text
* Button
  * A clickable box with text in it
  * Could be "sticky" by setting a property
    * This would allow it to behave like a radio button or even a checkbox
  * Could support image(s)
    * Background (clicked/non-clicked/being-clicked)
    * Foreground (instead of the text or next to the text)
* InputBox
  * An editable box with text in it
  * Integrated label support (shows up in the input box when empty)
* GroupBox
  * Sort of like a rectangular panel to place elements onto, with an outline and label
* ListBox
  * A scrollable list of items with text
* Tooltip
  * Text pop-up
  * Normally triggered on mouse over with a delay
* Slider
  * A slidable handle on a line
  * This could just contain a float value between 0 and 1 representing the position of the handle

GUIFactory class
----------------

This class manages GUI elements, and allows you to use a full GUI with a simple (programming) interface. That way you don't need to manually manage each element.

* Add/remove/access elements with string maps
  * There will be built in methods for creating the built in GUI elements, but it will support manually adding them as well as long as they are sub classes of BaseElement.
* Handle events and pass them to all elements
* Handles "focus" of elements and tab order (which is the order that you add the elements)
* Also could handle "linking" elements together and/or having elements in a group that are groupable
* Draws all of the elements
  * Order would go by type of element, so groupboxes first
* Could support loading the layout from a file.
  * Note you would still need to connect callbacks or handle the events manually, in order for the GUI to be functional.
* Could support loading styling information from a file.

Style settings
--------------

Styles could be applied globally and/or to specific elements or groups of elements.
* Still undecided on this. This might make more sense to only be global.
* This is probably still going to allow settings styles of different elements, so a button could be colored differently than an inputbox.
* Also note that these styles can be changed programmatically as well.

Some style settings could include:
* Font
  * Type, size, color, etc.
* Color
  * Outlines
  * Backgrounds
  * Text
* Lots more...

Layout settings
---------------

The layout settings will contain all of the elements that will exist in the GUI.

Some layout settings for each element:
* User-defined name/ID
* Type
  * Button/inputbox/etc.
* Position
  * This could be relative to other elements, or have absolute coordinates
* Size
  * Width/height
* Lots more...

Other
-----

### Possible custom extensions to this library:

* DropdownBox
  * Would just be a Button next to an InputBox that when clicked, would bring up a ListBox

* ColorfulInputBox
  * Parses color strings entered and changes the color based on that

* RuleGrid class
  * This will be used in Cells

* GameMenu class
  * Sort of its own full blown GUI for use with main menus in games.
  * Would mainly be a list of buttons that could have fancy styles and effects.
