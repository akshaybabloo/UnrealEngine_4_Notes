# UnrealEngine 4
UnrealEngine 4 using Blueprint visual scripting system.

> Note 1: This project is developed on Mac OSX 10.11.2 using UnrealEngine 4.10.1. It should work on Windows as well :ok_hand:.

> Note 2: Notes shown below may contain few lines from the original [UnrealEngine Documentation](https://docs.unrealengine.com) :stuck_out_tongue_winking_eye:.

## 1 Requirements

### 1.1 Software:

* [UnrealEngine 4.7+](https://www.unrealengine.com/) -> Gaming engine.
* [Maya](http://www.autodesk.com/products/maya/overview) or [3DS Max](http://www.autodesk.com/products/3ds-max/overview) -> For 3D modeling.
* [Photoshop](http://www.photoshop.com/products/photoshop) or [Illustrator](http://www.adobe.com/products/illustrator.html) -> For texture.

**Windows**

* Visual studio 2013 pro or community (as per the UnrealEngine documentation, this is installed automatically)

**Mac**

* Xcode 5.0 or above

### 1.2 Hardware:

According to [UnrealEngine documentation](https://docs.unrealengine.com/latest/INT/GettingStarted/RecommendedSpecifications/).

**Windows**

* Windows 7 or above
* A good graphic card that supports DirectX 11.
* Quad-core Intel or AMD, 2.5 GHz or faster processor
* 8 GB RAM or above

**Mac**

* Mac OSX 10.9.2 or above
* A good graphic card.
* Quad-core Intel, 2.5 GHz or faster
* 8 GB RAM or above

## 1.3 Bump Maps (or Normal Maps) generator

**Windows**

* [Awesome Bump](http://awesomebump.besaba.com/) -> Free :+1:
* [CrazyBump](http://www.crazybump.com/) -> Free :+1:
* [SSBump Generator](http://ssbump-generator.yolasite.com/) -> Commercial :expressionless:
* [Shadermap](http://shadermap.com/home/) -> Commercial :expressionless:
* [Filterforge](https://www.filterforge.com/) -> Commercial :expressionless:
* [B2M](https://www.allegorithmic.com/products/bitmap2material) -> Commercial :expressionless:

**Mac**

* [Awesome Bump](https://github.com/kmkolasinski/AwesomeBump) -> Free although you would have to build the files. Follow the instructions on their GitHub. :+1:
* [CrazyBump](http://crazybump.com/mac/) -> Free :+1:
* [Filterforge](https://www.filterforge.com/) -> Commercial :expressionless:
* [B2M](https://www.allegorithmic.com/products/bitmap2material) -> Commercial :expressionless:

**Online**

* [NormalMap Online](http://cpetry.github.io/NormalMap-Online/) -> Free :+1:

## 2 Creating project

Open Epic launcher and launch UnrealEngine. Goto `New Project`, under Blueprint (It is a node based approach where you don't have to write an code) tab click on `First Person`. Make sure there are no Starter contents (i.e. rocks, land etc...). Change the location of your project and file name to suit your needs. Once all the primary configurations are done, click on `Create Project`.

<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/NewProject.png" alt="New Project" width="800"></p>

## 3 UnrealEngine overview

<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/UnrealEngineNote.png" alt="New Project" width="800"></p>

> Tip 1: press `cmd + alt` (Mac) and move the cursor on an icon to get a quick help.

UnrealEngine (for me or maybe for everyone) is divided into seven parts:

1. *Modes* - This is where all the tool to build an environment is kept.
2. *Content browser* - All your project files can be browsed from this place.
3. *Details* - When you click an object (Actor, Pawns, Lights etc..) all its details are displayed here.
4. *World outliner (Outliner)* - What ever is available in the view port, can be seen here. Its like an Content browser but for you viewport.
5. *Toolbar* - Buttons to Save, Play etc.. are here.
6. *Search* - This is where you can search for help regarding an object.
7. *Viewport* - Your design area or the Editor.

## 4 Blueprint editor

<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/UnrealEngineEditor.png" alt="New Project" width="800"></p>

A `Blueprint` is a node based visual scripting system in which you would not need to code any action or effect an actor performs.

Blueprint is divided into six parts:

1. *Components* - Components of an actor.
2. *My Blueprint* - An outline of Blueprint function, scripts etc..
3. *Contents*
  1. *Viewport* - 3D view related to a particular actor.
  2. *Construction Script* - This contains Blueprint classes.
  3. *Event Graph* - This tab contains nodes. They perform events and functions while a game is played.
4. *Details* - Settings related to nodes.
5. *Toolbar* - Buttons to Save, Play etc.. are here.
6. *Search* - This is where you can search for help regarding an object.

## 5 Let's get started

### 5.1 Editing the environment

From the `World Outliner` lets remove `Cubes`, `Arena` and `Templatelabel`. We don't need them.

Next, the `FirstPersonCharacter` (under World Outliner) default action is to shoot balls. We would have to change it. To do that, beside the `FirstPersonCharacter` there is a blue link which says `edit FirstPersonCharacter`. This is the link to `Blueprint` `Editor`. Clicking on it will open a new window.

### 5.2 Blueprint editing

In `Event Graph` tab, look for `Pawn projectile` and delete it and also delete the nodes in it. We wouldn't be needing it. Once you have deleted the nodes, click on `Compile` button on the `Toolbar`, this will check for any errors. If no errors are found, a green tick would appear. Close this window.

### 5.3 Deleting unwanted meshes

Under `Content browser` Click on <img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/SourcePanel.png" alt="show or hide source panel" width="20"> to show source panel. In that click on `FirstPerson` and on the right window, double click on `Meshes`. This should open meshes associated to our project, in that delete `First Person Projectile` and `First Person Projectile`. You will get an window warning you that the meshes are still referenced. click on `Force Delete`. Then delete the `arms` and `gun` in the same way.

### 5.4 Creating Maya models

A Maya 2016 model is developed and is available in [UnrealEngine_4_Maya](https://github.com/akshaybabloo/UnrealEngine_4_Notes/tree/master/UnrealEngine_4_Maya) folder and `fbx` file is located in [Import](https://github.com/akshaybabloo/UnrealEngine_4_Notes/tree/master/Import) folder.

### 5.5 Importing `fbx` file

It is recommend that you always create multiple `fbx` files so that the UnrealEngine doesn't crash (the project is big). In this case its not a big import so I didn't do that.

In `Content Browser` click on `Import`, browse to `Import/house.fbx` and click `Open`. You will get a pop up `FBX Import Options` in that un-tick `Auto Generate Collision` (It creates a collision box or sphere etc.. for every object, we can do that manually). Then click on `Import All`.

Once you have imported your `fbx` file, the following files are generated:

* Meshes
* Texture (if it is associated with the model)
* Normal maps (if it is associated with the model)
* Bump maps (if it is associated with the model)

What I have done is that I have separated these files into their corresponding folders. For example, I have moved all my `meshes` to `Content/FirstPerson/Meshes/`.

### 5.6 Adding collusions

When you double click on the `house_no_doors` mesh, this will open the following editor

<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/StaticMeshEditor.png" alt="New Project" width="800"></p>

This editor is divided into five parts:

* *Viewport* - 3D view related to a particular actor.
* *Socket Manager* - For skeletons.
* *Details* - Settings related to an actor.
* *Toolbar* - Buttons to Save, Wireframe etc.. are here.
* *Search* - his is where you can search for help regarding an object.


There are different types of colliders. Namely

<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/CollusionMenu.png" alt="New Project" width="900"></p>

In this DOP means Discrete Oriented Polytope, which means that it will create box collision with bevels which is closest to the object or the actor. see [here](https://docs.unrealengine.com/latest/INT/Engine/Content/Types/StaticMeshes/HowTo/SettingCollision/index.html) to understand more about it.

We will be using Blueprint for the doors but for the rest of the building we will use `mesh collider`. In the `Details` tab (left to the editor). Scroll down and search for `Static Mesh Settings` in that tab change the `Collusion Complexity` `Default` to `Use Complex Collusion As Simple`. Save and close the editor.

>Note 3: Adding Mesh collusions will be expensive. That means the rendering time would take more time and the system will uses more frames per second depending on the number of mesh collusions. But for this example I have just created mesh collusion to make is simple.
