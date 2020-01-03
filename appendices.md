# Appendices

## Key-stroke level model (KLM)

| Operator | Description | Time (s) |
| --- | --- | --- |
| K | Keystroke or button press. | 0.28[a] |
| P | Pointing to a target on a display with a mouse. | 1.1[b]
| H | Homing the hand(s) on the keyboard or other device. | 0.4 |
| M | Mentally preparing for executing physical actions. | 1.35 |
| B[c] | Clicking a mouse button. | 0.2 |
Excerpt of used operators.[1]

a. Non-secretary typist average (40 words per minute).

b. Average. Varies with distance and target size according to Fitts's Law: t_p = 0.8 + 0.1 * log2(d / s + 0.5) s

c. Not present as a separate action in the original paper. Instead it is included as part of the homing motion.

## Test reports

In addition to questionnaires, we made use of automated user testing environments to help analyze user behaviour within our application. In addition to times measured for each task, generated test reports include a listing of actions conducted by the user complete with timestamps. These include the following:

- Opening up a dataset.
- Spawning a plot of a certain type.
- Assignment of attribute onto an axis.
- Deassignment of an attribute from a plot axis.
- Modification of attribute range.
- Flick-based plot rotation.
- Entering/leaving immersive mode.
- Accessing databrush panel.
- Accessing swatch (statistics) panel inside immersive mode.
- Change of plot scale.
- Change of plot scale in immersive mode.
- Movement in immersive mode.
- Plot deletion.

## Installation guide

In this section we will go over the setup procedures for components provided with this thesis. It is important to note that there are multiple builds available for each component - 1901 (January), 1908 (August) and 1912 (December). Intercompatibility of components from different builds is not guaranteed (i.e. the August build of Navigator may not be compatible with the December build of Manager).

### Navigator

Navigator, the VR component of our application, is provided as a collection of binary files. PC binaries require a computer running the latest version of Microsoft Windows 10 with Oculus software installed. Supported headsets include Oculus Rift and Oculus Rift S. To launch Navigator, open the exe file in a respective directory. Android binaries require Oculus Go or Oculus Quest standalone headsets with developer mode enabled.[2] These can be sideloaded using Android Debug Bridge and accessed via the Library interface under Unknown Sources.

By default, Navigator tries to connect to the public instance of Manager located at *cyberplot.tomires.eu*. If you would like to connect to a local version of Manager, please edit the */etc/hosts* file on your operating system (on Windows: *C:/Windows/System32/drivers/etc/hosts*). Insert the IP address of the server running Manager in the following format.

```
127.0.0.1 cyberplot.tomires.eu
```

### Manager

Manager, the web component of our application, is provided in form of source code bundled with an installation script. Functionality has been tested on a clean install of Ubuntu 18.04 LTS. To begin setup, navigate inside the folder and run the provided script as superuser by using the following commands:

```
chmod u+x install.sh
sudo ./install.sh
```

Follow on-screen prompts and then wait for the installation to finish. Manager instance should then be accessible using a standard web browser.

## Plugins

Included are sample integrations for Python and R. Before use, please modify the *DEFAULT_URL* variable or specify the *serverUrl* argument when calling any of the functions. It should point to an IP address or a hostname of a machine running an instance of Manager.

## Video transcripts

The following are transcripts from videos that were created to explain the different parts of our application and also the user interface and controls of our virtual reality component in 3DOF and 6DOF versions.

### Introduction

Hello, and welcome to Cyberplot, a fresh new way to look at your data. Cyberplot consists of three components - plugins, Manager and Navigator.

You can use plugins to integrate Cyberplot into your programming environment of choice, such as Python or R. Using our API integrations is easy, just follow the instructions.

Manager allows you to upload data straight from your computer. This is also where you can edit existing datasets and share them with others.

Once you have added some data, it's time to put on your VR headset and launch Cyberplot Navigator. In order to learn more about controls in VR, please watch the next videos in our tutorial series.

Ready to get started? Launch Cyberplot Manager by going to the following site and create an account. Next, you will want to associate a headset with your account. When you first launch Navigator, you will be presented with a 5-digit pairing code. Log into Manager and open up the VR headset management window. Enter the pairing code and you're good to go! We'll see you in VR.

### 6DOF controls

Hello there. Are you ready to interact with your data in VR? Continue watching to learn the basics of Cyberplot Navigator! In this video, we presume that you are using a headset that includes positional tracking, such as the Oculus Rift, HTC Vive, any of Windows Mixed Reality headsets or the Oculus Quest.

After launching into Navigator, hold down the grip button on one of your controllers. Doing so displays what we call a data brush. Start by selecting the dataset that you would like to work with. Your data brush includes basic information about the currently selected dataset as well as listing of all the attributes. Each attribute includes a label, data type and either a histogram or data preview. If there is a larger number of attributes, you can move between pages by moving the analog stick on your controller left or right. Navigator allows you to interact with multiple datasets at the same time. To load a new dataset, click the corresponding button. 

Next, let's learn how to add a plot. Point at the floor and hold the trigger. Move the pointer to a plot type you wish to create and release the trigger. To move the plot around your person, point at it and hold the trigger. You can also move it closer or further away from you by using your controller's analog stick. Make sure you are still holding the trigger while doing so. If you wish to delete the plot, just drag it far away from you and release the trigger. Plots can also be rotated by using the flick gesture we have introduced earlier. In order to resize the plot, select it using both of your controllers and move them apart from one another while holding the trigger buttons.

### 3DOF controls

Hi, and welcome to Cyberplot, a new way to interact with your data in virtual reality. In this video, we will go over controls for headsets that only support rotational tracking like the Oculus Go.

After launching into Navigator, you will be presented with a list of all your datasets. Start by selecting the dataset that you would like to work with. You should now be able to see the attributes on what we call a data brush. Your data brush includes basic information about the currently selected dataset as well as listing of all the attributes. Each attribute includes a label, data type and either a histogram or data preview. If there is a larger number of attributes, you can move between pages by swiping the touchpad. Navigator allows you to interact with multiple datasets at the same time. To load a new dataset, click the corresponding button. You can hide your data brush at any time by pressing the back button on your controller. To show the data brush, just press the button again.

Next, let's learn how to add a plot. Point at the floor and hold the trigger. Move the pointer to a plot type you wish to create and release the trigger. To move the plot around your person, point at it and hold the trigger. You can also move it closer or further away from you by using your controller's touchpad. Make sure you are still holding the trigger while doing so. If you wish to delete the plot, just drag it far away from you and release the trigger. Plots can also be rotated by using the flick gesture we have introduced earlier. You can also enter the freeform rotation mode by pointing on the plot and pressing down on the touchpad. Press the touchpad again, to exit. In order to resize the plot, hold the trigger and twist your wrist like so.

### Shared 3DOF/6DOF

You now know how to create plots and load datasets. The last thing you need to learn is how to work with attributes. To assign an attribute to a plot, just drag the attribute from the data brush onto one of the axes using the trigger button. You can also map an attribute onto a non-spatial feature of the plot such as color or size. In order to remove an assignment, just click on the attribute's label. You can also change the bounds of selected spatial attributes by clicking on the scales. This is useful for more complex datasets.

Lastly, let's learn about versioning. Versioning allows you to keep multiple copies of a single dataset. After enabling versioning inside Cyberplot Manager, you can change between the versions straight from your data brush. And that covers the basics of Cyberplot Navigator. Have fun exploring your data.

1. (klm) https://dl.acm.org/citation.cfm?doid=358886.358895
2. (godevmode) https://developer.oculus.com/documentation/mobilesdk/latest/concepts/mobile-device-setup-go/