Sreeraj Chintham <schintha1@stevens.edu>
[Github - Project1](https://github.com/sreerajchintham/Project1)
### Time spent on the project - 20 hours
### HOW I TESTED MY CODE
I tested my code using two maps given in the project description.After adding the extension I tested my code using a Map I made to work my extensions.
    
### Bugs
No major bugs were encountered.However I had to change my approach once even after using classes.
### Issues
The issue I encountered was to seperate the methods between two classes.

### Extensions
I chose 1. Directions become verbs
        2. Drop verb
        3. Locked Doors
        
 ### 1. Directions become verbs
      
     I created a list which contained directions which is also called **directions**.
     I had a bridge method which takes the input string and redirects to respective verb methods.It is called **action(self)**.
     If the input string contained only directions the action method redirects it to a method called **abbrev**.
     The abbrev method reconstructs the variable which stores input string in this case **self.playerchoice** so that it contains **go** verb.
     Then abbrev method calls the go verb function with the reconstructed input string .
     I did not need any new methods or verb functions for the extension.
     The Extension enables us to use directions as verbs and also facilitates abbreviations for unusual exits like northwest.
     
     
 ### 2. Drop Verb
      
     **Drop** verb as indicated in documents is opposite to the **get** verb .
     Although I did not introduce any new variables, I created to new verb method **drop**.
     I had a bridge method which takes the input string and redirects to respective verb methods.It is called **action(self)**.
     In the action method it calls drop method upon detecting "drop" in the input string.
     Simultaneously, the input string is split on spaces and casted into list called **pclist**.
     *step search and remove*
     If length of pclist is 2 then the second element is searched in **inv** which is a list containing inventory(Items picked up and not yet dropped)
     If the second element is in **inv** then the item is removed and added to the itemlist which goes by **items** it gets added to room.
     Then it formats the **inv_string** which is used to output inventory.
     If second element of pclist not in **inv**  then the resultant print will come up.
     If length of pclist is 1 then the resultant print will come up.
     If the pclist has more than two elements then the item that should be dropped has spaces in it.
     
     Hence by slicing the input string we can the **name of item** with which the **step search and remove** will repeat.
     Finally the method will call method **playerinput** which prompts "what would you like to do?"
     
### 3. Locked Doors

    Unlike other Extensions, to know whether an exit is locked we need to include some kind of information about it in the map file.
    In this Extension I chose the locked information to be in dictionary of which the Keys are **Exits which are locked** and Items are the ** Item required to unlock the exit ** .
    If a certain exit is not mentioned in the **locked** dictionary then the exit is unlocked.
    And there may not be locked dictionary at all in some rooms.
    Exactly one Item is required to open a single Exit at a point of time.
    And once you try to enter a locked room the gameengine automatically checks your inventory for required item.
    If the item is not present in the inventory the player will not be allowed to use the exit.
    I created locked method and self.locked(dictionary which stores the *locked* dictionary of THE CURRENT ROOM) variable.
    The locked method is made to be a bridge method between **action** method  and **go** verb method.
    If input string contains go and has and **pclist** (list of input string split by spaces) has length of 2 .
    The locked method searches the second element of pclist in *locked* dictionary .
    And upon finding it few prompts are printed and the **inv**(inventory) is check for ** Item required to unlock the exit ** in *locked* dictionary.
    If **inv**(inventory) contains the ** Item required to unlock the exit ** then the door will be unlock and the player proceeds to the next room(by invoking **go** method).
    
    If **inv**(inventory) does not contains the ** Item required to unlock the exit **  then the door will be locked and **playerinput** method which prompts "what would you like to do?" will be invoked
    


    
    
    
    
    
    
    
     
     
     
     
     
     
     


