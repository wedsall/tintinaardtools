# Tintin++ Aardwolf Tools

This is a work-in-progress Tintin++ based version of Aardwolf's popular search-and-destroy plugin. This is made for people like me who, for whatever reason, don't want to use the mushclient. 

This project contains modified code from other projects:
1. https://github.com/theixle/aardwolf-tintin - the GMCP module
2. https://tintin.sourceforge.io/board/viewtopic.php?p=8046&sid=704c49de6c4cccca5d1dcaa4a68e5c4c - the mysql class

How to get this working:
1. Create a mysql database and and import the aard.sql schema
2. Import into your existing tintin++
```
#read mysql.tin;
#read gmcp.tin;

#map create;
#MAP READ {$logdir/map-all.tt};
```
3. (in-game) tag roomchars on
4. Walk around in-game and let the mapper database build!

# Commands

mobsearch (ms): Search for a mob within your current area
```
ms lady
Mob Search in zone bliss (limit 20):
roomname roomid mobname
A Lovely Path to the Lawn 29987 A noble lady is here trading gossip.
Corner of the Lawn 30026 A noble lady is here trading gossip.
Chairs by the Platform 30024 A noble lady is here trading gossip.
...
```

mobsearch all (msall): Search within all areas
```
msall guard
Mob Search in All Zones (limit 20):
areaname mobname roomid roomname
kobaloi A short, stocky individual appears to be standing guard. 10693 A Mountain Ledge
kobaloi A Kobalos in dark robes stands on guard. 10716 Before a Gated Cavern
kobaloi A Palace Keeper guards the palace. 10729 Before the Palace of the Kobaloi
kobaloi A Kobalos stands here, guarding the entrance. 10768 Kobaloi Subterranean Fish Ponds
talsa A bodyguard is walking down the halls, probably on a job right now. 26950 Entrance to Palace
talsa This guard is assigned to this hallway, and you wonder at its importance. 26951 Palace Intersection
...
```

room search (rs): Search for a room id and zone
```
rs kitchen
Room Search (limit 20):
areaname roomid roomname
landofoz 506 Kitchen
talsa 26927 Kitchen
bliss 30015 Kitchen
bliss 30021 Small Kitchen Garden
```

# Usage Example

1. pick up campaigns and quests
2. fully explore the areas that you get with quest targets. this will populate your mapper and the mobs database
3. After fully exploring the area(s), use the tools to locate your campaign and quest targets. identify your target's roomid and use #map run {number}
4. the more you do and populate the mapper, the easier it will be to locate targets that you've already seen

# Known issues - todo list

1. The database ends up with duplicate mobs due to color codes
