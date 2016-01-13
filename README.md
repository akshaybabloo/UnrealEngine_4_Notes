# UnrealEngine 4
UnrealEngine 4 using Blueprint visual scripting system.

> **Note 1:** This project is developed on Mac OSX 10.11.2 using UnrealEngine 4.10.1. It should work on Windows as well :ok_hand:.

> **Note 2:** Notes shown below may contain few lines from the original [UnrealEngine Documentation](https://docs.unrealengine.com) :stuck_out_tongue_winking_eye:.

## 1 Requirements
### 1.1 Software:
- [UnrealEngine 4.7+](https://www.unrealengine.com/) -> Gaming engine.
- [Maya](http://www.autodesk.com/products/maya/overview) or [3DS Max](http://www.autodesk.com/products/3ds-max/overview) -> For 3D modeling.
- [Photoshop](http://www.photoshop.com/products/photoshop) or [Illustrator](http://www.adobe.com/products/illustrator.html) -> For texture.

**Windows**
- Visual studio 2013 pro or community (as per the UnrealEngine documentation, this is installed automatically)

**Mac**
- Xcode 5.0 or above

### 1.2 Hardware:
According to [UnrealEngine documentation](https://docs.unrealengine.com/latest/INT/GettingStarted/RecommendedSpecifications/).

**Windows**
- Windows 7 or above
- A good graphic card that supports DirectX 11.
- Quad-core Intel or AMD, 2.5 GHz or faster processor
- 8 GB RAM or above

**Mac**
- Mac OSX 10.9.2 or above
- A good graphic card.
- Quad-core Intel, 2.5 GHz or faster
- 8 GB RAM or above

## 1.3 Bump Maps (or Normal Maps) generator
**Windows**
- [Awesome Bump](http://awesomebump.besaba.com/) -> Free :+1:
- [CrazyBump](http://www.crazybump.com/) -> Free :+1:
- [SSBump Generator](http://ssbump-generator.yolasite.com/) -> Commercial :expressionless:
- [Shadermap](http://shadermap.com/home/) -> Commercial :expressionless:
- [Filterforge](https://www.filterforge.com/) -> Commercial :expressionless:
- [B2M](https://www.allegorithmic.com/products/bitmap2material) -> Commercial :expressionless:

**Mac**
- [Awesome Bump](https://github.com/kmkolasinski/AwesomeBump) -> Free although you would have to build the files. Follow the instructions on their GitHub. :+1:
- [CrazyBump](http://crazybump.com/mac/) -> Free :+1:
- [Filterforge](https://www.filterforge.com/) -> Commercial :expressionless:
- [B2M](https://www.allegorithmic.com/products/bitmap2material) -> Commercial :expressionless:

**Online**
- [NormalMap Online](http://cpetry.github.io/NormalMap-Online/) -> Free :+1:

## 2 Creating project
Open Epic launcher and launch UnrealEngine. Goto `New Project`, under Blueprint (It is a node based approach where you don't have to write an code) tab click on `First Person`. Make sure there are no Starter contents (i.e. rocks, land etc...). Change the location of your project and file name to suit your needs. Once all the primary configurations are done, click on `Create Project`.
<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/NewProject.png" alt="New Project" width="800"></p>

## 3 UnrealEngine overview
<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/UnrealEngineNote.png" alt="New Project" width="800"></p>

> **Tip 1:** press `cmd + alt` (Mac) and move the cursor on an icon to get a quick help.

UnrealEngine (for me or maybe for everyone) is divided into seven parts:
1. _Modes_ - This is where all the tool to build an environment is kept.
2. _Content browser_ - All your project files can be browsed from this place.
3. _Details_ - When you click an object (Actor, Pawns, Lights etc..) all its details are displayed here.
4. _World outliner (Outliner)_ - What ever is available in the view port, can be seen here. Its like an Content browser but for you viewport.
5. _Toolbar_ - Buttons to Save, Play etc.. are here.
6. _Search_ - This is where you can search for help regarding an object.
7. _Viewport_ - Your design area or the Editor.

## 4 Blueprint editor
<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/UnrealEngineEditor.png" alt="New Project" width="800"></p>

A `Blueprint` is a node based visual scripting system in which you would not need to code any action or effect an actor performs.

Blueprint is divided into six parts:
1. _Components_ - Components of an actor.
2. _My Blueprint_ - An outline of Blueprint function, scripts etc..
- _Contents_
  1. _Viewport_ - 3D view related to a particular actor.
  2. _Construction Script_ - This contains Blueprint classes.
  3. _Event Graph_ - This tab contains nodes. They perform events and functions while a game is played.

- _Details_ - Settings related to nodes.
3. _Toolbar_ - Buttons to Save, Play etc.. are here.
4. _Search_ - This is where you can search for help regarding an object.

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
There are two ways to import an `fbx` file into the project that fits the scale of the project. In this case I am using maya.
- You can scale up the models while importing `fbx` files into UnrealEngine. When you import an `fbx` file you will get an option
<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/ImportFBX.png" alt="New Project" width="500"></p>

  When ever I import the models I usually scale it up to `100`.

- The other way is to change the Maya environment so that the models can be imported as it is. You can check out this tutorial [here](http://www.worldofleveldesign.com/categories/ue4/ue4-set-up-maya-grid-to-match-unreal-engine4.php).

It is recommend that you always create multiple `fbx` files so that the UnrealEngine doesn't crash (if the project is big). In this case its not a big import so I didn't do that.

In `Content Browser` click on `Import`, browse to `Import/house.fbx` and click `Open`. You will get a pop up `FBX Import Options` in that un-tick `Auto Generate Collision` (It creates a collision box or sphere etc.. for every object, we can do that manually). Then click on `Import All`.

Once you have imported your `fbx` file, the following files are generated:
- Meshes
- Texture (if it is associated with the model)
- Normal maps (if it is associated with the model)
- Bump maps (if it is associated with the model)

What I have done is that I have separated these files into their corresponding folders. For example, I have moved all my `meshes` to `Content/FirstPerson/Meshes/`.

### 5.6 Adding collusions
When you double click on the `house_no_doors` mesh, this will open the following editor
<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/StaticMeshEditor.png" alt="New Project" width="800"></p>

This editor is divided into five parts:
- _Viewport_ - 3D view related to a particular actor.
- _Socket Manager_ - For skeletons.
- _Details_ - Settings related to an actor.
- _Toolbar_ - Buttons to Save, Wireframe etc.. are here.
- _Search_ - his is where you can search for help regarding an object.

There are different types of colliders. Namely
<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/CollusionMenu.png" alt="New Project" width="900"></p>

In this DOP means Discrete Oriented Polytope, which means that it will create box collision with bevels which is closest to the object or the actor. see [here](https://docs.unrealengine.com/latest/INT/Engine/Content/Types/StaticMeshes/HowTo/SettingCollision/index.html) to understand more about it.

We will be using Blueprint for the doors but for the rest of the building we will use `mesh collider`. In the `Details` tab (left to the editor). Scroll down and search for `Static Mesh Settings` in that tab change the `Collusion Complexity` `Default` to `Use Complex Collusion As Simple`. Save and close the editor.

> **Note 4:** Adding Mesh collusions will be expensive. That means the rendering time would take more time and the system will uses more frames per second depending on the number of mesh collusions. But for this example I have just created mesh collusion to make is simple.

### 5.7 Creating Blueprints
All my Blueprints are place in `FIrstPersonBP/Blueprints/`. To create a blueprint right click on the `Content Browser` and click on `Blueprint Classes`, this will pop-up a window which will ask you to select a parent class that should look something like this
<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/PickParentClass.png" alt="New Project" width="700"></p>

We will create a simple `Actor` for this blueprint and name it as `DoubleDoor`. Double click on it to open Blueprint editor. Now drag the `door_left` and `door right` into the blueprint editor. Then click on `compile` and `save` from the Toolbar.

### 5.8 Add models to the Viewport
Goto meshes folder and drag all the meshes and drop it on the view port. If the models looks out of placement, you can `0` the transformation in from the details tab.

Now from the Blueprints folder drag and drop `DoubleDoor` blueprint into the viewport. Once this is done place this in the exact place where the door should be. Save the scene.

## 6 Material
### 6.1 Editing materials
When you move the meshes to the viewport in UnrealEngine editor, some times depending on the software used to export `fbx` files, the material is added to the meshes automatically and some times not. The materials may include Normals, Bump maps, occlusions etc.. To manually add these to an existing material you would have to do the following:
- On the left side of the editor under Details (make sure you have selected the model from the Viewport), search for Materials, in that tab you can see different elements associated to the static mesh. Double click on a material this will open Material editor.
<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/NaterialEditor.png" alt="New Project" width="800"></p>

  It consists the following components:
  1. _Preview_ - Preview of the changes made to the material.
  2. _Viewport_ - Node editor.
  3. _Palette_ - Node menu.
  4. _Details_ - Details of a selected node.
  5. _Toolbar_ - Consists of save, apply etc..
  6. _Search_ - Search for components related to UnrealEngine.

- In the viewport there are three node `Constant` (Custom metallic effect), `lambert2` (actual texture from Maya) and `Texture Sample` (Texture added to lambert2).

  The `Texture Sample` node consists of RBG channels as shown in the image below
<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/TextureNode.png" alt="New Project" width="170"></p>

- Once you have done the necessary changes then you should click on `Apply` and then `Save`.

### 6.2 Shine to `lambert7` texture
Let try to give a shine to one of the material which is used in as texture to the out side railings. Do the following:
1. Goto texture folder and double click on `lambert7` texture, this should open material editor.
2. Delete `None` node.
3. lets create a `Constant3Vector`, you can right click and search for it or you can drag or double click the node from `Palette` tab or press and hold `3` and left click on the mouse.
4. Connect this node to `Base Color`.
5. Double click on the color to pop out color palette. Change the color as you like. Click on `Save` once done.
6. Create a `Constant` and connect it to `Specular`. Change the value to `0.6`.
7. Create a constant and connect it to `Roughness`. Change the value to `0.2`.
8. Save and close.

### 6.3 Creating glass
1. Double click on `Glass` material.
2. Delete `None` node.
3. if a node is selected, un select it by click outside. In the `Details` tab, under `Material` change `Blend Mode` -> `Translucent`. Under `Translucency` tab uncheck `Separaye Translucency` and change the `Lighting Mode` -> `Surfae TranslucencyVolume`.
4. Next add `Constant3Vector` and make a dark green color. Add two constants `0.2` for Metallic and `2` for Specular. Then add `Lerp` (Linear Interpolation) by pressing `L` and clicking left mouse button and connect it to Opacity. Next add a `Fresnel_Function` connect the `Result` to `Alpha` of `Lerp` node. Two constants with value `0` connected to `A` and `1` connected to `B` of `Lerp` node.
5. Now copy two `Constants`, `Lerp` and `Fresnel_Function` and paste it. Connect the result to Refraction.
6. Create another constant of `0` and connect it to Roughness.

The nodes should look something like this:
<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/GlassNode.png" alt="New Project" width="700"></p>

### 6.4 Adding reflections
In the `Modes` tab search for `Sphere Reflection Capture` and drag it near the glass door. In the `Details` tab search for `Reflection Capture` and change the value of `Influence Radius` this will change the outer radius of the sphere.

If any changes are made do not forget to click on `Update Captures`.

## 7 Lighting
### 7.1 Adding lights
In `Modes` tab, click on `Lights`, I will add a `Spot Light` on top of my table by dragging it into the Viewport. You can change the `Perspective` to `Top` to make it easy to move the spot light.

Once you have placed your lights click on the small arrow beside `Build` button in the Toolbar and click on `Build Lights Only`. At this point if you have multiple number of light on a surface you will get a small red mark on the lights and you might get error while building the lights.

### 7.2 IES Profiling
An IES profiles gives you the shave and size of the light rays that come from a spotlight. IES files are usually given out by the lights manufactures, lets consider [GE Lighting](http://www.gelighting.com/LightingWeb/aus/products/technologies/led/led-r63-dimmable/overview/), if you scroll down in that web site you can find IES/LDT files.

You can use this file by importing it into UnrealEngine and drag & drop on the `IES Texture` under `Light Profiles` by selecting a spot light.

An example of these can be seen [here](http://www.derekjenson.com/3d-blog/ies-light-profiles).

## 8 Adding animations and interactions
### 8.1 Adding sockets
Double click on `door_hinge`. Add a box collider to it. To add sockets to the hinge do the following

from the menu bar click on `Window -> Socket Manager`. On the left side of the screen below you will see a tab called `Sock Manager` in that click on `Create Socket` and name the socket as `SocketDoorL` and place it as shown in the image below. Like wise create another socket and place it as shown.
<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/GlassNode.png" alt="New Project" width="700"></p>

Save and close the window.
