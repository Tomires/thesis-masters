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

a. Non-secretary typist average (40 words per minute)

b. Varies with distance and target size according to Fitts's Law: t_p = 0.8 + 0.1 * log2(d / s + 0.5) s

c. Not present as a separate action in the original paper. Instead it is included as part of the homing motion.

## Video transcripts

The following are transcripts from videos that were created to explain the different parts of our application and also the user interface and controls of our virtual reality component in 3DOF and 6DOF versions.

### Introduction

Hello, and welcome to cyberplot, a fresh new way to look at your data. Cyberplot consists of three components - plugins, manager and navigator.

You can use plugins to integrate cyberplot into your programming environment of choice, such as Python or R. Using our API integrations is easy, just follow the instructions.

Manager allows you to upload data straight from your computer. This is also where you can edit existing datasets and share them with others.

Once you have added some data, it's time to put on your VR headset and launch Cyberplot Navigator. In order to learn more about controls in VR, please watch the next videos in our tutorial series.

Ready to get started? Launch Cyberplot Manager by going to the following site and create an account. Next, you will want to associate a headset with your account. When you first launch Navigator, you will be presented with a 5-digit pairing code. Log into Manager and open up the VR headset management window. Enter the pairing code and you're good to go! We'll see you in VR.

### 6DOF controls

Hello there. Are you ready to interact with your data in VR? Continue watching to learn the basics of Cyberplot Navigator! In this video, we presume that you are using a headset that includes positional tracking, such as the Oculus Rift, HTC Vive, any of Windows Mixed Reality headsets or the Oculus Quest.

After launching into Navigator, hold down the grip button on one of your controllers. Doing so displays what we call a databrush. Start by selecting the dataset that you would like to work with. Your databrush includes basic information about the currently selected dataset as well as listing of all the attributes. Each attribute includes a label, data type and either a histogram or data preview. If there is a larger number of attributes, you can move between pages by moving the analog stick on your controller left or right. Navigator allows you to interact with multiple datasets at the same time. To load a new dataset, click the corresponding button. 

Next, let's learn how to add a plot. Point at the floor and hold the trigger. Move the pointer to a plot type you wish to create and release the trigger. To move the plot around your person, point at it and hold the trigger. You can also move it closer or further away from you by using your controller's analog stick. Make sure you are still holding the trigger while doing so. If you wish to delete the plot, just drag it far away from you and release the trigger. Plots can also be rotated by using the flick gesture we have introduced earlier. In order to resize the plot, select it using both of your controllers and move them apart from one another while holding the trigger buttons.

### 3DOF controls

Hi, and welcome to Cyberplot, a new way to interact with your data in virtual reality. In this video, we will go over controls for headsets that only support rotational tracking like the Oculus Go.

After launching into Navigator, you will be presented with a list of all your datasets. Start by selecting the dataset that you would like to work with. You should now be able to see the attributes on what we call a data brush. Your databrush includes basic information about the currently selected dataset as well as listing of all the attributes. Each attribute includes a label, data type and either a histogram or data preview. If there is a larger number of attributes, you can move between pages by swiping the touchpad. Navigator allows you to interact with multiple datasets at the same time. To load a new dataset, click the corresponding button. You can hide your databrush at any time by pressing the back button on your controller. To show the databrush, just press the button again.

Next, let's learn how to add a plot. Point at the floor and hold the trigger. Move the pointer to a plot type you wish to create and release the trigger. To move the plot around your person, point at it and hold the trigger. You can also move it closer or further away from you by using your controller's touchpad. Make sure you are still holding the trigger while doing so. If you wish to delete the plot, just drag it far away from you and release the trigger. Plots can also be rotated by using the flick gesture we have introduced earlier. You can also enter the freeform rotation mode by pointing on the plot and pressing down on the touchpad. Press the touchpad again, to exit. In order to resize the plot, hold the trigger and twist your wrist like so.

### Shared 3DOF/6DOF

You now know how to create plots and load datasets. The last thing you need to learn is how to work with attributes. To assign an attribute to a plot, just drag the attribute from the databrush onto one of the axes using the trigger button. You can also map an attribute onto a non-spatial feature of the plot such as color or size. In order to remove an assignment, just click on the attribute's label. You can also change the bounds of selected spatial attributes by clicking on the scales. This is useful for more complex datasets.

Lastly, let's learn about versioning. Versioning allows you to keep multiple copies of a single dataset. After enabling versioning inside Cyberplot Manager, you can change between the versions straight from your databrush. And that covers the basics of Cyberplot Navigator. Have fun exploring your data.

1. https://dl.acm.org/citation.cfm?doid=358886.358895