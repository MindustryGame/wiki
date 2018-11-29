This is a full tutorial on how to setup and utilize power. To properly understand proper ratios, please see the Analysis tab. 

## Intro

Many blocks later on in the game need power to run. To determine if a block needs power, click on the '?' icon when clicking on a block in the build screen. The block will need power if it says:

```
Power
    Power Capacity: *n* power units
    Power use: *n* power units/second
```

You can also determine if a block needs power by hovering your mouse over it and checking the yellow icons on the left. If it has a lightning icon with a red mark, that means it requires power.

All of the blocks in the power build menu (in the build menu, the lightning bolt icon category) do not need power, but will either produce or distribute power. 

### Power Capacity
Power capacity is how much power the block stores. If it is producing extra power, it will start to store this excess power in it's power capacity. This is shown with a **yellow bar** when clicking on the block. Both power production blocks and power consumtion blocks have power capacity. If excess power is being produced, first the production block will fill, and then the power generation block. (WHEN WILL BATTERY PRIORITIZE? need to check build60)  

- If the yellow bar is empty or very low, most or all of it's input power is being used.
- If the block has a full yellow bar, it making more than enough power and will stop producing power. 
- If the block has a perfect power input to power use ratio, the yellow bar will not fill. This is because there is no excess power. 

### Power Use
A block that uses power has both a power-use stat and a power capacity stat. The block will use all power that is needed to meet its power use requirements. If not enough power is supplied, a crossed off lightning icon will appear when clicking on the block, the yellow bar will be low, and the block will have drastically reduced production.
The rate of reuced production is proportional to the amount of power needed. For example, a drill with only half the power will drill at a quarter of the speed! 

## Setting up Power

The first thing to be aware of is **power generation blocks share power when they are touching**. This includes power nodes!

<img src="https://i.imgur.com/cvhgmBZ.png" width=40%>

*Two small power nodes are touching each other while the third one is touching the Pulverizer, which is getting full power. Note that the touching nodes and node touching Pulverizer are not wired with a node connection, only proximitity touching.*

<img src="https://i.imgur.com/bu5gtnn.gif" width=20% align="right">

Small Power Nodes, which are 1x1 in size, connect to a maximum of 4 things. Because power generation blocks touching act like one big power source, a node can connect to any block in the network. 

To connect something using a power node, click the node. The range of the node will show up. Then all available options for connection will appear as a red circle. Currently connected blocks will be a purple circle with a yellow wire connection. Once the node has used all of its available connections, all possible blocks will have a red circle with a red cross in it.

### Power recommendations:

1. Coal must be burnt in a Combustion Generator in order to power Silicon Smelters.
2. Once Silicon is made, Solar Panels should be built. Optional: Combustion Generators can be upgraded to Turbine Generators. They are much more efficent but require water. (POWER LOSS? see ratios. need to research)
3. A Thorium Reactor should be made next. It gives 66 power/s with 30 Thorium and proper cooling. For proper cooling, please see Ratios page. 
4. Large Solar Panels are very useful, and very easy to use. They require no work and give a good amount of power.


## Power Blocks
//not sure what to put here!

## Tips and Tricks
Tip 1
- Power Grid (WIP)




