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
