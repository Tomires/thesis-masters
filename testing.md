# Testing

In this chapter, we will compare the efficiency of our application against that of its contemporary alternatives introduced in chapter 2, introduce our testing methodology and present some of the findings.

## Example task

The following table lists all KLM operations necessary to complete the task of creating a three-dimensional scatter plot as outlined in the second chapter. It presumes we are logged into Manager and have already associated a VR headset with our account.

| Operator | Description | Time (s) |
|---|---|---|
| M | Initiate opening a file | 1.35 |
| M | Find *Add new dataset* button on sidebar | 1.35 |
| PB | Point at the button and press it | 1.3 |
| PB | Select *Local file* | 1.3 |
| PB | Click on *Next* | 1.3 |
| PB | Click on *Select file* | 1.3 |
| PB | Select file and double click it | 1.3 |
| PB | Click on *Next* | 1.3 |
| M | Put on the VR headset with Navigator running | 1.35 |
| B | Display the data brush by holding the grip button  | 0.2[a] |
| PB | Point on a dataset and press the trigger | 1.3 |
| B | Hide the data brush by releasing the grip button | 0.2[a] |
| PBPB | Point on the ground, hold trigger, select scatter plot icon, release the trigger | 2.6 |
| B | Display the data brush by holding the grip button | 0.2[a] |
| M | Locate the data brush | 1.35[b] |
| 2*(PBPB) | Drag attributes onto two of the spatial dimensions | 5.2 |
| PB | Rotate the plot | 1.3 |
| PBPB | Drag an attribute onto the remaining spatial dimension | 2.6 |
| PBPB | Drag an attribute onto the color dimension | 2.6 |
| B | Hide the data brush by releasing the grip button | 0.2[a] |
| PB | Point at the scale and press the trigger to slice the plot | 1.3 |

a. Only applies to 6DOF version
b. Only applies to 3DOF version

The total time necessary to complete the tasks is 29.55 seconds for 6DOF and 30.1 seconds for 3DOF versions, considerably faster than with contemporary tools introduced in chapter 2.

## User testing

In addition to smaller user feedback sessions that took place over the entire course of development, two complex testing runs have been conducted in August and December 2019. In this section, we will discuss the testing methodologies and share key findings.

### August test

This round of testing took place at Tohoku University in Sendai, Japan with three participants taking part. Testing sessions were designed to take approximately 45 minutes of time, however the typical length of each session was closer to one hour. The schedule was as follows:

1. Questionnaire - section on previous experience.
2. Introduction to data visualization.
3. Showcase of ParaView.
4. Showcase of Tableau.
5. Questionnaire - section on traditional tools.
6. Introduction to Cyberplot.
7. Demo of Manager and plugins.
8. Demo of Navigator on Oculus Go (3DOF).
9. Demo of Navigator on Oculus Rift (6DOF).
10. Timed tests incorporating all components.
11. Questionnaire - Cyberplot-specific section.

Sections 4-5 and 8-9 were conducted in random order in order to mitigate the effects of confounding influences of practice. Participants have been selected from a diverse range of backgrounds, with emphasis on a large variance of experience with virtual reality and the fields of data analysis, statistics and visualization. Timed tests utilized a modified version of Navigator capable of creating automatic logs and displaying instructions to the user. Testing tasks are detailed further into this section.

We began by asking the participants a series of questions about their background:

- Do you have any prior experience with virtual reality? (Yes/No, list devices if any)
- Do you experience motion sickness in virtual reality? (Not at all/Occasionally/Often)
- Are you familiar with the area of data analytics? (Yes/No)
- How much experience do you have with programming? (No experience/Little experience/Some experience/Lot of experience)
- Have you ever used a BI/visual analytics tool in the past? (Yes/No, list software if any)

Afterward completing the first part of our questionnaire, the users were shown two pieces of traditional visualization software - ParaView and Tableau. They were instructed to load a multivariate dataset from file, look up basic statistical information of each attribute, rename an attribute label, create a scatter plot, assign attributes onto spatial axes and color feature of the plot and lastly, to change the range of values shown on spatial axes. Second part of the questionnaire followed:

- I felt ParaView was easy to use. (1-5)
- I felt Tableau was easy to use. (1-5)

After answering the two questions, the participants were shown a video introducing them to our application. They were then instructed to launch Manager, create a user account, add a dataset, change attribute type, rename an attribute label, share a dataset with another user, accept an incoming share request and associate a fresh copy of Navigator with their account. A short demo of our plugin system had the participants load a dataset from R Studio.

Brief demos of 3DOF and 6DOF versions of Navigator were then given, each preceded by a short tutorial video. Participants were instructed to load a previously added dataset, create a plot, change plot assignments, position the plot in space, toggle between different versions of a single dataset and delete the plot. The 3DOF version was tested on an Oculus Go, while Oculus Rift was used for testing the 6DOF version of Navigator.

A timed test was then administered with participants being given the following tasks:

1. Load dataset "Iris".
2. Create a box plot.
3. Move plot to desired position.
4. Move plot to desired position and scale it appropriately.
5. Delete the box plot.
6. Create a scatter plot.
7. Move plot to desired position.
8. Move plot to desired position and scale it appropriately.
9. Delete the scatter plot.
10. Create a new scatter plot in front of you.
11. Assign "Sepal Width" to one of spatial axes.
12. Assign "Petal Width" to another spatial axis.
13. Assign "Sepal Length" to the third spatial axis.
14. Assign "Class" to plot"s color.
15. Slice the plot to isolate the green cluster using Petal Width.
16. Create a new scatter plot.
17. Load dataset "Abalone".
18. Assign "Diameter" to one of spatial axes.
19. Assign "Length" to another spatial axis.
20. Assign "Whole weight" to the third spatial axis.
21. Assign "Sex" to plot"s color.
22. Assign "Rings" to plot"s size.
23. Slice "Whole weight" from 0.8 to 2.0.

After concluding the timed test, participants were given the third and final part of our questionnaire. There were tasked to choose whether they agree with the following statements on a scale from 1 to 5:

- Cyberplot is easier to use than traditional 2D visualization tools.
- I was able to easily grasp information presented to me.
- Moving objects in 3D space felt intuitive.
- The size of the virtual environment felt adequate.
- I perceived benefit in percepting data using cyberplot compared to using traditional 2D tools.
- The process of getting data from computer to virtual reality felt straightforward.
- Scale labels on plot were legible.
- Changing slice boundaries was easy.
- Free-form rotation felt natural.
- Using cyberplot felt fun.
- Plot nodes felt three-dimensional.
- I did not encounter issues with controls in VR. (white/3DOF headset)
- I did not encounter issues with controls in VR. (black/6DOF headset)
- Using the plugin system was easy.

An open-ended question followed - "Is there anything you found frustrating about cyberplot? Are there any features or plugin integrations you would like to see implemented?".

Participants were then asked to rank the following plots in the order of their interest:

- 3D bar plot
- map plot
- parallel coordinate plot
- surface plot
- globe plot

Testing concluded with a standardized Simulator Sickness Questionnaire (SSQ).[1]

#### Findings

**TODO**

### December test

**ADD DECEMBER BUILD TEST**
leading questions modified
**BUGS DISCOVERED**

1. (sickness) https://www.researchgate.net/publication/221494074_Simulator_Sickness_in_Mobile_Spatial_Sound_Spaces