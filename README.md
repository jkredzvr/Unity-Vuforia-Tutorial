<a href="http://www.colorado.edu/studentgroups/vrarclub/">
    <img src="https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/VRLogo.png" alt="CU VRAR Club logo" title="CU VRAR Club logo" align="center" height="350" />
</a>

Simple Unity Vuforia Application
======================

The repository contains a simple augmented reality application using [Vuforia](https://vuforia.com), built on the [Unity](unity.com) Platform.  This app, deployed on a laptop, will use the webcamera and Vuforia unity package to recognize a selected image marker and project a 3D model above the marker on the screen.  

GIF OF RECOGNIZING IMAGE

Please download and install all software and register for Unity & Vuforia accounts before attending the event.

## Table of content
- [Installation and Account Registration](#installation-and-account-registration)
- [Unity Project Setup](#unity-project-setup)
- [Vuforia AR Camera Set Up](#vuforia-ar-camera-set-up)
- [Vuforia License Key](#vuforia-license-key)
- [Vuforia Target Image Database](#vuforia-target-image-database)


- [Target Image Database](#page-setup)
    - [Upload the page tree file](#upload-the-page-tree-file)
    - [Go to the import view](#go-to-the-import-view)
    - [Import the uploaded page tree file](#import-the-uploaded-page-tree-file)

- [Target Image Setup in Unity](#setting-up-target-image-in-unity)
- [Projected Virtual Object Setup](#setting-up-a-virtual-object-to-be-projected)
- [Playing the AR App](#playing-the-ar-app)
- [Bonus: Changing animations with Voice Control](#bonus)

- [License](#license)
- [Links](#links)


## Installation and Account Registration
Install the following programs/packages and create accounts for Unity and Vuforia.  Unity Personal Version is a free beginner friendly development platform for 2D, 3D, VR and AR applications.  Note: When installing Unity 5.6, it will default to a Unity folder in program files.  If you have downloaded a previous version of Unity and want to keep it, rename the default folder name.  

* [Unity 5.6 Installation](https://unity3d.com/unity/whats-new/unity-5.6.0)
* [Unity ID Registration](https://id.unity.com/en/conversations/207adc60-e15a-49a3-a9b0-3339b2cae79b012f?view=register)
* [Vuforia Account Registration](https://developer.vuforia.com/user/register)
* [Vuforia Unity Package Download](https://developer.vuforia.com/downloads/sdk)


## Unity Project Setup
First open up Unity 5.6 and create a new project in folder location and project name you desire.  Make sure that the Unity project is selected as 3D.

 ![Saving Project Screenshot](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/1_projectsave.png) 

Once Unity has opened, we will import the Vuforia Unity Package to allow of our Unity Augmented Reality application the ability to recognize images/3D models using the laptop camera, and track and display virtual objects on this image.  Import the Vuforia Unity Package by navigating to Assets/Import Packages/Custom Packages at the top of the menu toolbar.

![Import Package](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/2_import%20vuforia.png) 

Locate the [Vuforia Unity Package](https://developer.vuforia.com/downloads/sdk) downloaded earlier, and click open.

![Import Package 2](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/2_import%20vuforia_2.png) 

An import unity package popup menu will appear asking which files should be imported.  Click on all, then click import.

![Import Package 3](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/2_import%20vuforia_3.png) 

Another popup message will ask you have backed up your project.  Go ahead and click that you have made a copy.

## Vuforia AR Camera Set Up
Once the Vuforia package has been imported, the Assets/Vuforia folder will appear in the Project Folder located in the bottom panel of the Unity program.  This folder houses scripts and "Prefab" gameobjects of the Vuforia components that can be dragged into your Unity application to build an augmented reality app.  The AR Camera Prefab will give Vuforia access to a camera feed (either laptop, camera, HMD head mount display) and recognized images or "markers" set in your Vuforia account.  Navigate to the Assets/Vuforia/Prefabs folder and drag the ARCamera prefab into either the Hiearchy window or Scene Window.

![AR Cam Setup](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/3_ARCamSetup.png) 

When the ARCamera prefab is dragged into your scene or hierarchy, the gameobject will appear in the hiearchy window indicating that it is now part of scene of your Unity application.  Configure the Vuforia settings to connect with your Vuforia account by first selecting the ARCamera in the hiearchy window to view its components in the Inspector, and then clicking on the Open Vuforia Configuration button in the Vuforia Behaviour Component.

![AR Cam Setup 2](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/3_ARCamSetup_2.png) 
    
After clicking Open Vuforia Configuration, the Inspector view will show the Vuforia Configuration file where you will paste your Vuforia License Key     
    
![AR Cam Setup 3](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/3_ARCamSetup_3.png) 

## Vuforia License Key
Log into the [Vuforia License Manager](https://developer.vuforia.com/license-manager) page  with the [Vuforia Account](https://developer.vuforia.com/user/register) you created.  Click on Add License Key to create a free key enabling your Unity application to use Vuforia's image recognition services up to a specified limit.

![Vuforia License Key](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/4_licensekey.png) 

Select Project Type: Development, create a name for the app, and click next to continue.

![Vuforia License Key 2](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/4_licensekey_2.png)

The next page will have the Vuforia license key for your app, which can be copied and pasted into Vuforia Configuration App License key text field in the Unity application. 

![Vuforia License Key 3](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/4_licensekey_3.png)

## Vuforia Target Image Database
Go back to Vuforia License Manager page, click on Target Manager link, and click on Add Database button to set up a set of images your AR app will recognize.  Provide a name for the database of images that will be recoginzed by the app and make sure Type:Devices is selected.

![Vuforia Target Images](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/5_TargetManager.png)
![Vuforia Target Images 2](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/5_TargetManager_2.png)
![Vuforia Target Images 3](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/5_TargetManager_3.png)

When the database is created, click on the database link and click on Add Target Button to start adding the images to be recognized.  

![Vuforia Target Images 4](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/5_TargetManager_4.png)

Vuforia can recognize different types of targets ranging from 2D images, 3D objects, and shapes.  For reliable image recognition and tracking, Vuforia suggests chosing images and objects with the following characteristics: 
      
| Attribute | Example |
| --- | --- |
| Rich in detail | Street-scene, group of people, collages and mixtures of items, or sport scenes |
| Good contrast | Has both bright and dark regions, is well lit, and not dull in brightness or color |
| No repetitive patterns | Grassy field, the front of a modern house with identical windows, and other regular grids and patterns |
      
Further information and suggestions for improving image recognition and tracking stability can be found [here](https://library.vuforia.com/articles/Solution/Optimizing-Target-Detection-and-Tracking-Stability).

For this sample app, we will choose the following image.  Download this image or copy it from https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/VuforiaTargetImage.png, and upload it the target Image field.

![Vuforia Target Images 4](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/VuforiaTargetImage.png)

For the width input, enter the actual width (in meters) of the object or image that will be recogized.  Since I will be printing the image on an 8.5" x 11" letter paper, I'll input 8.5" -> .259m.

Lastly give the image target a unique name that will be saved in the database, before clicking on the Add Button

![Vuforia Target Images 5](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/5_TargetManager_5.png)

Back on the Target Manager page, the uploaded target will appear with a star rating indicating whether the target image will be reliably recognized and tracked by the Vuforia software.  If you choose to upload your own 2D images or images of objects, upload several different images and make sure that you have at least 4-5 star ratings or reliable tracking.  Feel free to upload multiple different image targets if you want your app to recognize more than one image/object.

![Vuforia Target Images 6](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/5_TargetManager_6.png)

After uploading your image targets, click on the Download Database(All) button and select Unity Editor to download image database files into a Unity package. 

Go back into the Unity program and navigate Assets/Import Packages/Custom Packages and select the downloaded Image Database Unity Package.

![Vuforia Target Images 7](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/5_TargetManager_7.png)

After importing all the database image Unity package, the VuforiaConfiguration component should show up with a checkbox to select a database to be loaded.  Click on this option, and click on Activate checkbox that appears next.

![Vuforia Target Images 8](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/5_TargetManager_8.png)

## Setting up Target Image in Unity
With the Vuforia Configurations loaded with the image databse set in your Vuforia account, we'll set up a virtual scene for our objects to appear when an image or object is recognized.  

In Unity, navigate to the Assets/Vuforia/Prefabs folder and drag the ImageTarget prefab from the folder to the Hierachy View.  The ImageTarget prefab acts as the recognized image/object target for where our virtual objects will be tracking its position.  If a virtual objects above the ImageTarget, when laptop camera sees our actual image or target in the real world, the AR app will place and track our relative to where the ImageTarget is virtually...  

![Unity Target](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/6_UnityTarget.png)

Selecting the ImageTarget in the Hiearchy view, select the image database that was imported from the dropdown menu next to Database.

![Unity Target 1](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/6_UnityTarget_1.png)

## Setting Up a Virtual Object to be projected

Now lets project a virtual object over the our image target when our app recognizes the target.  Click on the Unity Asset Store Tab and click on the Log In button.  After logging in you will access to download free and paid assets from the Asset Store that can be added into your application.  Assets can range from 3D Models, environments, characters, textures, shaders, scripts and many other components used to build a game or application.

![Virtual Asset](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/7_VirtualAsset.png)

We will be downloading the free Unity-Chan asset, which is a rigged 3D model with animations.  In the search bar, search for Unity Chan and click on the "Unity-Chan" Model link.

![Virtual Asset 1](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/7_VirtualAsset_2.png)

Click on the Import Button and wait for it be loaded into your project.  A popup box will ask which files to import, which you will click All, and Import.

After Unity-Chan import is complete, navigate to Assets/UnityChan/Prefabs folder and drag the unitychan prefab into the Hiearchy Window. 

![Virtual Asset 2](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/7_VirtualAsset_3.png)

You will see the UnityChan model standing above the imagetarget, so when the app recognizes the target in the real world, the UnityChan model will appear how it is currently placed in Unity.  Right now the image target was set to be a width of .259m (8.5"), and looking at UnityChan in the Unity program, she will be too large to appear on the app screen.  To remedy this we will scale down the size of UnityChan.  

First click and select UnityChan from the Hiearchy Window.  In the inspector window, change the Transform: Scale x,y,z values to shrink UnityChan.  I chose .1, but you can select modify it to your liking.

![Virtual Asset 3](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/7_VirtualAsset_4.png)

The last step for setting up our Virtual object, is to drag our object and set it as a child of the ImageTarget.  This lets the Vuforia know what gameobject or virtual object should appear when a target image/object is recognized.  To set UnityChan as a child to the ImageTarget, simply drag the UnityChan gameobject in the hiearchy, and drop it on top of ImageTarget.  It should be located below the Image Target as a child gameobject.

![Virtual Asset 3](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/DragUnityChan.gif)

## Playing the AR App

To test out your app, you will need to print out the target image for the app to recognize.  Click on the Play button above the scene view to start the app in Unity.  If the default camera is properly recognized by Vuforia, you should be able to see the live camera feed in the Unity Gamemode screen.  Hold up the printed target image in front of the camera, and your AR app should recognize the target and generate the Virtual object (Unity-chan for this demo) where you have placed it in your scene.

You will also notice several buttons on the sides of the Unity Gamemode screen.  Those are pre-made buttons provided by the Unity-Chan object to cycle through Unity-Chan's different facial reactions and poses.

![Virtual Asset 3](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/PlayingARApp.gif)

Voila! Now you have a Unity AR scene that generates a virtual object on a recognizes a target image.  Use this project as a base and modify it to your needs by doing the following:

* Changing the target images with your own images or models in Vuforia
* Changing the virtual model and animations
* Controlling the virtual model's animation with button presses or recognized voice keywords
* Having multiple recognized images/models that generate different interactie virtual objects
* Deploying the Unity scene as an .exe or mobile app 

## Bonus 


## License




