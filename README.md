# DualUniverse-OreMonitor
This set of LUA scripts will help you setup screens that display ore name | quantity in tons | % of how full a container is | status color coded based on ore % levels

## Elements required

- 5 Screens M
- 5 Programming Boards
- 21 Item containers
- 1 Switch
- 1 Relay

## Control links Setup
These are the same type of links you use to link industries and containes in build mode. Each Programming board can support up to 10 links. You could modify the script/links to use less programming boards but I wanted to keep things organized/separated and also somewhat future proof if they add more ores per tier in the future.

** Important ** you must rename each slot to match the names in the scripts **

1. Programming Board 1 control links:
  - screen (same name in each Programming board for the slot linking to the screen)
  - bauxite ( linking to containing this particular ore )
  - coal ( linking to containing this particular ore )
  - hermatite ( linking to containing this particular ore )
  - quartz ( linking to containing this particular ore )
  - switch (sends on/off signals to the relay to turn on/off all the screens and programming boards)
  
2. Programming Board 2 - 5 control links:
- screen
- item container  ( rename to match the ores in each tier )
- item container  ( rename to match the ores in each tier )
- item container  ( rename to match the ores in each tier )
- item container  ( rename to match the ores in each tier )

3. Relay links:
link the relay to each screen and programing boards 2-5. So that by activating programming board one a signal will be sent to the switch which transmits that signal to the relay and the relay turns on/of every screen/programming board at once.

## Filters Setup
Under Unit add the following filters/code

1. start()
  `unit.setTimer("Live",1)`
  `switch.activate()` ** ONLY in Programming board 1 **
2. stop()3
  `screen.clear()` ( not required but you can use to clear the html on the screen by deactivating the programming board linked to the screen )
3. tick(Live) (note that the name you enter for this tick needs to match the name of the timer entered in the start() filter above )

## Script setup
In the lua editor enter the code for each script that matches the programming board. i.e programming board 1 under tick enter the code in T1 script and programing board 2 enter the code for T2 script etc
  
