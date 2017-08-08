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




### TYPO3 extension repository

If you want to install Aimeos into your existing TYPO3 installation, the [Aimeos extension from the TER](https://typo3.org/extensions/repository/view/aimeos) is recommended. You can download and install it directly from the Extension Manager of your TYPO3 instance.

For new TYPO3 installations, there's a 1-click [Aimeos distribution](https://typo3.org/extensions/repository/view/aimeos_dist) available too. Choose the Aimeos distribution from the list of available distributions in the Extension Manager and you will get a completely set up shop system including demo data for a quick start.

### Composer

The latest version can be installed via composer too. This is especially useful if you want to create new TYPO3 installations automatically or play with the latest code. You need to install the [composer](https://getcomposer.org/) package first if it isn't already available:
```
php -r "readfile('https://getcomposer.org/installer');" | php -- --filename=composer
```

In order to tell composer what it should install, you have to create a basic `composer.json` file in the directory of you VHost. It should look similar to this one:

It will install TYPO3 and the latest Aimeos TYPO3 extension in the `./htdocs/` directory. Afterwards, the Aimeos composer script will be executed which copies some required files and adds a link to the Aimeos extensions placed in the `./ext/` directory. To start installation, execute composer on the command line in the directory where your `composer.json` is stored:
```
composer update
```

## Vuforia Target Setup 

### Registration

* Log into the TYPO3 back end
* Click on ''Admin Tools::Extension Manager'' in the left navigation
* Click the icon with the little plus sign left from the Aimeos list entry (looks like a lego brick)
* If a pop-up opens (only TYPO3 4.x) choose ''Make updates'' and "Close window" after the installation is done

**Caution:** Install the **RealURL extension before the Aimeos extension** to get nice looking URLs. Otherwise, RealURL doesn't rewrite the parameters even if you install RealURL afterwards!

![Install Aimeos TYPO3 extension](https://aimeos.org/docs/images/Aimeos-typo3-extmngr-install.png)

### Target Setup

Afterwards, you have to execute the update script of the extension to create the required database structure:

![Execute update script](https://aimeos.org/docs/images/Aimeos-typo3-extmngr-update-7.x.png)

## Page setup

The page setup for an Aimeos web shop is easy if you import the [standard page tree](https://aimeos.org/fileadmin/download/Aimeos-pages_two-columns_2.1.6.t3d) into your TYPO3 installation.

### Go to the import view

* In Web::Page, root page (the one with the globe)
* Right click on the globe
* Move the cursor to "Branch actions"
* In the sub-menu, click on "Import from .t3d"

![Go to the import view](https://aimeos.org/docs/images/Aimeos-typo3-pages-menu.png)

### Upload the page tree file

* In the page import dialog
* Select the "Upload" tab (2nd one)
* Click on the "Select" dialog
* Choose the file you've downloaded
* Press the "Upload files" button

![Upload the page tree file](https://aimeos.org/docs/images/Aimeos-typo3-pages-upload.png)

### Import the uploaded page tree file

* In Import / Export view
* Select the uploaded file from the drop-down menu
* Click on the "Preview" button
* The pages that will be imported are shown below
* Click on the "Import" button that has appeared
* Confirm to import the pages

## License

The Aimeos TYPO3 extension is licensed under the terms of the GPL Open Source
license and is available for free.


