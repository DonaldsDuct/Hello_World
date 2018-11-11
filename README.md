import maya.cmds as cmds
import pymel.core as pm

#grabbing vertex number and object name
mySelection=pm.ls(selection = True)
print mySelection
print mySelection[0]
#if mySelection[0] is not type('MeshVertex') or mySelection > 2 or mySelection < 2:
#    pm.error("Invalid selection. Select two vertices")
if len(mySelection[0]) > 1:
    mySelection = mySelection[0]
    

my_list = []

for Vertex in mySelection:

    #Grabbing vertex position on cube, need to grab it from world :/
    mySelPosition=pm.xform(Vertex,q=True,t=True, ws=True)
    print mySelPosition
    
    
    my_list.append (mySelPosition)
    
    print(my_list)
    

pos1 = my_list[0]
pos2 = my_list[1]

#Will build the dimension ruler from vertex to vertex, uses distance to measure
myRuler = pm.distanceDimension( sp=(pos1), ep=(pos2))
print pm.listConnections(myRuler)

MyLocators = pm.listConnections(myRuler)



list = [1,2]
print len(list)

