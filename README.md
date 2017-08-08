<a href="http://www.colorado.edu/studentgroups/vrarclub/">
    <img src="https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/VRLogo.png" alt="CU VRAR Club logo" title="CU VRAR Club logo" align="Center" height="350" />
</a>



Simple Unity Vuforia Application
======================

The repository contains a simple augmented reality application based on Vuforia, built on the Unity Platform.  This app, deployed on a laptop will use the webcamera and Vuforia unity package to recognize a selected image marker and project a 3D model above the marker on the screen.  

GIF OF RECOGNIZING IMAGE

Please download any software and register for Vuforia accounts before attending the event as it will take some time to download and install Vuforia.


## Table of content

- [Installation and Account Registration](#install-registration)

- [Installation](#installation)
    - [TER](#typo3-extension-repository)
    - [Composer](#composer)
- [Vuforia Target Setup](#Vuforia Target Setup)
    - [Extension](#extension)
    - [Database](#database)
- [Page setup](#page-setup)
    - [Upload the page tree file](#upload-the-page-tree-file)
    - [Go to the import view](#go-to-the-import-view)
    - [Import the uploaded page tree file](#import-the-uploaded-page-tree-file)
- [License](#license)
- [Links](#links)


## install-registration

Install the following programs/packages and create accounts for Unity and Vuforia.  Unity Personal Version is a free beginner friendly development platform for 2D, 3D, VR and AR applications.

* [Unity 5.6 Installation](https://unity3d.com/unity/whats-new/unity-5.6.0)
* [Unity ID Registration](https://id.unity.com/en/conversations/207adc60-e15a-49a3-a9b0-3339b2cae79b012f?view=register)
* [Vuforia Account Registration](https://developer.vuforia.com/user/register)
* [Vuforia Unity Package Download](https://developer.vuforia.com/downloads/sdk)


## Installation

1. Setup Unity
    2. Setup account
    3.  Download Vuforia Package 
    4.  New Project
    ![Saving Project Screenshot](https://github.com/jkredzvr/Unity-Vuforia-Tutorial/blob/master/Screenshots/1_projectsave.png) 
    5. Import Vuforia Package
2.  Create Vuforia Account
    Login
    Add licensce key (development) , create app name, copy license key
    
3.  Go back into Unity, drag AR kit, located in... 
    Drag AR kit prefab into scene
    click on kit in hiearchy to inspect properties
    Vuforia behaviour component, click on edit configuration and paste the key into the App Licence Key text field

4.  Go back to Vuforia developer website , and click on Target Manager
      click create image target database, images that your AR app will recognize,with devices selected
      Now add a target image, which allows for a flat image, 3D image for recognition
      We will choose a 2D image for this example
      For good tracking and image recognition, Vuforia suggests the following, 
      
| Attribute | Example |
| --- | --- |
| Rich in detail | Street-scene, group of people, collages and mixtures of items, or sport scenes |
| Good contrast | Has both bright and dark regions, is well lit, and not dull in brightness or color |
| No repetitive patterns | Grassy field, the front of a modern house with identical windows, and other regular grids and patterns |
      
      further info and suggestions for improving image recognition and tracking stability can be found [here](https://library.vuforia.com/articles/Solution/Optimizing-Target-Detection-and-Tracking-Stability)



### TYPO3 extension repository

If you want to install Aimeos into your existing TYPO3 installation, the [Aimeos extension from the TER](https://typo3.org/extensions/repository/view/aimeos) is recommended. You can download and install it directly from the Extension Manager of your TYPO3 instance.

For new TYPO3 installations, there's a 1-click [Aimeos distribution](https://typo3.org/extensions/repository/view/aimeos_dist) available too. Choose the Aimeos distribution from the list of available distributions in the Extension Manager and you will get a completely set up shop system including demo data for a quick start.

### Composer

The latest version can be installed via composer too. This is especially useful if you want to create new TYPO3 installations automatically or play with the latest code. You need to install the [composer](https://getcomposer.org/) package first if it isn't already available:
```
php -r "readfile('https://getcomposer.org/installer');" | php -- --filename=composer
```

In order to tell composer what it should install, you have to create a basic `composer.json` file in the directory of you VHost. It should look similar to this one:
```json
{
    "name": "vendor/mysite",
    "description" : "My new TYPO3 web site",
    "minimum-stability": "dev",
    "prefer-stable": true,
    "repositories": [
        { "type": "composer", "url": "https://composer.typo3.org/" }
    ],
    "require": {
        "typo3/cms": "~8.7",
        "aimeos/aimeos-typo3": "dev-master"
    },
    "extra": {
        "typo3/cms": {
            "cms-package-dir": "{$vendor-dir}/typo3/cms",
            "web-dir": "htdocs"
        }
    },
    "scripts": {
        "post-install-cmd": [
            "Aimeos\\Aimeos\\Custom\\Composer::install"
        ],
        "post-update-cmd": [
            "Aimeos\\Aimeos\\Custom\\Composer::install"
        ]
    }
}
```
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

![Import the uploaded page tree file](https://aimeos.org/docs/images/Aimeos-typo3-pages-import.png)

Now you have a new page "Shop" in your page tree including all required sub-pages.

## License

The Aimeos TYPO3 extension is licensed under the terms of the GPL Open Source
license and is available for free.


