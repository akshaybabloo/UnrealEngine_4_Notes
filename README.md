# UnrealEngine-4-notes
UnrealEngine 4 Notes

> Note 1: This project is developed on Mac OSX 10.11.2 using UnrealEngine 4.10.1. It should work on Windows as well :ok_hand:.

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

* [Awesome Bump](http://awesomebump.besaba.com/) -> Free
* [CrazyBump](http://www.crazybump.com/) -> Free
* [SSBump Generator](http://ssbump-generator.yolasite.com/) -> Commercial

**Mac**

* [Awesome Bump](https://github.com/kmkolasinski/AwesomeBump) -> Free although you would have to build the files. Follow the instructions on their GitHub.
* [CrazyBump](http://crazybump.com/mac/)

**Online**

* [NormalMap Online](http://cpetry.github.io/NormalMap-Online/)

## 2 Creating project

Open Epic launcher and launch UnrealEngine. Goto `New Project`, under Blueprint (It is a node based approach where you don't have to write an code) tab click on `First Person`. Make sure there are no Starter contents (i.e. rocks, land etc...). Change the location of your project and file name to suit your needs. Once all the primary configurations are done, click on `Create Project`.

<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/NewProject.png" alt="New Project" width="700"></p>

## 3 UnrealEngine overview

<p align="center"><img src="https://raw.githubusercontent.com/akshaybabloo/UnrealEngine_4_Notes/master/Screenshots/UnrealEngineNote.png" alt="New Project" width="700"></p>

> Tip 1: press `cmd + alt` (Mac) and move the cursor on an icon to get a quick help.

UnrealEngine (for me or maybe for everyone) is divided into seven parts:

1. *Modes* - This is where all the tool to build an environment is kept.
2. *Content browser* - All your project files can be browsed from this place.
3. *Details* - When you click an object (Actor, Pawns, Lights etc..) all its details are displayed here.
4. *World outliner (Outliner)* - What ever is available in the view port, can be seen here. Its like an Content browser but for you viewport.
5. *Toolbar* - Buttons to Save, Play etc.. are here.
6. *Search* - This is where you can search for help regarding an object.
7. *Viewport* - Your design area or the Editor.
