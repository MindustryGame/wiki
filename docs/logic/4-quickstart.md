>  How Can I Get Started With Logic?
>  

(insert proper introduction here)


### Section 1: Print & Print Flush

We begin with the basics:

1) Place a processor (any type wil work).
2) Place a message block nearby.
3) Click on the processor - its range and a write button will pop up.
4) Click on the message box while the overlay is open: it should say `message1` above it.

![image](https://user-images.githubusercontent.com/45698812/115095955-13f6d480-9ed8-11eb-90d9-e2f3f7e1ba8a.png)

5) Click the write button below the processor. 
6) Click the `Add` button then click `Print`.
8) Enter `"Hello World!"` into the box - make sure that there are double quotes.
9) Click `Add` again and select `Print Flush`.
10) Exit out - you should see "Hello World!" in the message block!

![image](https://user-images.githubusercontent.com/45698812/115096044-6cc66d00-9ed8-11eb-85fe-59315e2c46b6.png)

Congrats, you just wrote your first program!
Let's get some other commands involved.

### Section 2: Sensor & Control

Printing is great, but the greatest power in using logic comes in being able to control the world around you

1) Remove the code in the processor
2) Place a door and a switch near the processor
3) Click `Add` and select `Sensor`
4) The default parameters are `result`, `@copper`, and `block1`
5) Delete `@copper` and replace it with `@enabled`
6) Delete `block1` and replace it with `switch1`
* as the name implies, sensor can *sensor* information from the outside world
* this code will read the state (`@enabled`) of the switch (`@switch1`) and put it into a variable named `result`
7) Click `Add` and select `Control`
8) Delete `block1` and replace it with `door1`
9) Delete `0` and replace it with `result`
10) Exit out - clicking the switch should now toggle the door!

### Section 3: Radar
TODO


(below should probably be split into a separate file, but i just want to lay out a general order of things)

### Section 4: Get Link
### Section 5: Set and Operation
### Section 6: Draw & Drawflush
### Section 7: Jump & End
### Section 8: Unit Control
### Section 9: Misc.
oddities e.g.
en/disabled sorter behavior, @counter


### Further Reading
- link to glossary
- list of mods
- other guides
