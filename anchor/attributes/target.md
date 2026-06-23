# Target

This attribute specify how to show the link content .

## Values

* _blank : It opens the link in a new window. <br>
* _self : It is the default value. It opens the linked document in the same frame.<br>
* _parent : It opens the linked document in the parent .<br>
* _top : It opens the linked document in the full body of the window. <br>
* framename : It opens the linked document in the named frame.

## How to specify the target ?

* **Place** : If the link will go to a section in my site let target _self is proper to let user in my world. <br>

* **Security** : If the user inputs his data in form and clinks in privasy polisy link <br> if we let target _self the user will lose his data so make target is _blank is reqiured .

### Default value 
***_self***

### Notes :
*Any invalid value or wrong using a valid attribute the browser will use default target value but using non-existent iframe name then the browser will open a new tab or window with the same name that is not exist.*


<br>

#### conclusion
_blank --> We use this value if the link will go outside site or inside site with user effort.<br>
_self --> We use this value if the link will go inside site without user effort to protect . <br>