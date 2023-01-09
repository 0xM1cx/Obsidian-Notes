## DSA Simulator (Unity)

### Day 1 (1/7/2023)
- I started setting up the project, making the different bars which represents my numbers. I made a total of 32 vertical bars including a square beneath each bar to act as my position for when I do other complex algorithms like bubble sort wherein I will have to move/arrange each vertical bar to their proper placement.
- I coded the Linear Search Algorithm with a visual identifier. The visual identifier works like this, the current bar being search will turn blue and if that bar is the bar we are searching for it will remain blue and a pop up text saying "ITEM FOUND" will appear and the simulation will stop. If that bar is not the one we are searching for then it will turn back to white and move on to the next bar until it found the right one.
- I learned how to instantiate text, find gameobjects and put them in a list, well you can put them in any data structure but I just chose a list because the size of the list can dynamically change depending on the number of items you add to it. I also learned how to access the sprite renderer component to change the color of the sprite. Lastly, I learnt how to fiddle with button and how they have a area where you can put in script or game objects that have the desired script you want, and how you can set which method gets invoked when that button is pressed.

### Day 2 (1/7/2023)
- WHAT I DID: I Finished the Linear Search Algorithm Simulation and added new features such as restart button. I also added a real time indicator of the current item being searched as well as the item to search for. 
- ISSUES: When clicking the restart button multiple times, it doesn't really do a full restart, it resets the text at the top that says "ITEM FOUND" or "ITEM NOT FOUND". Furthermore, it does also start the searching from the first index, the problem is that when I restart the simulation the previous simulation, if its still searching, will continue to search.