# aria-pressed

*This attribute change the state of the button in a11y tree*

## values

* **false** (default) --> it sounds the screen reader that {Not pressed} .
* **true** --> it sounds the screen reader that {pressed} .

**so it use state corner in a11y to notice this butto is pressed or not**

<br>

# aria-expanded

*This aria attribute is like aria-pressed it warns the screen reader if menu or list is expenden or not*

# aria-haspopup

*This attribute warns the screen readers if this button will open popup or not and the shape of it*

## Values

-- Every one of this values notice the user ther is a popup will appear to prepare but every one has a different shape  or not specific shape or even has not any popup ...

* false (default) --> this warns the user this button has not any popup .
* true --> it warns the user this button has a popup without specify a shape .
* menu --> it opens menu .
* dialog --> it opens dialog .
* tree --> it opens tree .
* listbox --> it opens listbox .
* grid --> it opens grid .

### When i use every value ?

**if the popup will show :**<br>
<ol>
<li> list of command "menu" . </li>
<li> list of Values (days, hours, names, products ...) "listbox"  </li>
<li> Hierarchical data "Tree"  </li>
<li> Grid data like files "Grid"  </li>
<li> dialog data "dialog"  </li>
</ol>

# aria-describedby 

*This attribute put more details for button name in a11y tree imagine that you have removal button his name "remove" but*
*but the user do not know what he will remove or he know if you want to put warns before remove or delete something*

**It take an id to this details from another element**

# aria-controls 

*Thsi attribute is linking between button and its content elements in a11y tree*

**It take the IDs of its elements.**

# aria-selected 

*This attribute is initiated for choosing from a group you want to choose a specific choice like days months years names etc*

### values

* true -> is selected .
* false -> is not selected .
* mixed -> partial selected - select a part but not all like shoose a part of task but not all of it-
* undefined -> this is not selectable button .

# aria-checked

This attribute is initiated for checkbox combo box as it as it is not focus in group it focus <br>
in the button checked or not it used for choosing your wants in a large choices like in visual studio in choosing<br>
the tools for your technology in sidebar so you can choose what you want <br>
but in selection you choose a specific number of selects <br>

### values

* true -> is checked .
* false -> is not checked .
* mixed -> partial checked - check a part but not all like shoose a part of task but not all of it-
* undefined -> this is not checkable button .