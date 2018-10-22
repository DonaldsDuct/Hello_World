# Hello_World
Place for my Py code for Maya

import maya.cmds as cmds

#grabbing vertex number and object name
mySelection=cmds.ls (selection = True)
print mySelection

#Grabbing vertex position on cube, need to grab it from worl :/
mySelPosition=cmds.xform(mySelection,q=True,t=True)
print mySelPosition
#Will build the dimension ruler from vertext to vertex, uses distance to measure
build = cmds.distanceDimension(sp=(mySelPosition), ep=mySelPosition)

#I can see the world co-ordinates after I jig the verts in the world, it's probably because I'm tired and crazy but that might be something to take note of, I just need to some how take those values and have the code read the values in real time without having to manually put it in all the time. The x form code gets the correct co ordinates it's just a matter of the distance ruler reading those
