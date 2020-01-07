# Testing

In this chapter, we will compare the efficiency of our application against that of its contemporary alternatives introduced in the first chapter, introduce our testing methodology and present some of the findings.

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

The total time necessary to complete the tasks is 29.55 seconds for 6DOF and 30.1 seconds for 3DOF versions, considerably faster than with contemporary tools introduced in the first chapter.

## User testing

In addition to smaller user feedback sessions that took place over the entire course of development, two complex testing runs have been conducted in August and December 2019. In this section, we will discuss the testing methodologies and share key findings.

### August test

This round of testing took place at Tohoku University in Sendai, Japan with four participants taking part. Testing sessions were designed to take approximately 45 minutes of time, however the typical length of each session was closer to one hour. The schedule was as follows:

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

After completing the first part of our questionnaire, participants were shown two pieces of traditional visualization software - ParaView and Tableau. They were instructed to load a multivariate dataset from file, look up basic statistical information for each attribute, rename an attribute label, create a scatter plot, assign attributes onto spatial axes and color feature of the plot and lastly, to change the range of values shown on spatial axes. Second part of the questionnaire followed:

- I felt ParaView was easy to use. (1-5, where 5 denotes full agreement)
- I felt Tableau was easy to use. (1-5)

After answering the two questions, the participants were shown a video introducing them to our application. They were then instructed to launch Manager, create a user account, add a dataset, change attribute type, rename an attribute label, share a dataset with another user, accept an incoming share request and associate a fresh copy of Navigator with their account. A short demo of our plugin system had the participants load a dataset from R Studio.

Brief demos of 3DOF and 6DOF versions of Navigator were then given, each preceded by a short tutorial video. Participants were instructed to load the previously added dataset, create a plot, change plot assignments, position the plot in space, toggle between different versions of a single dataset and delete the plot. The 3DOF version was tested on an Oculus Go, while Oculus Rift was used for testing the 6DOF version of Navigator.

A timed test was then administered with participants being given the following tasks:

1. Load dataset *Iris*.
2. Create a bar plot.
3. Move plot to desired position.
4. Move plot to desired position and scale it appropriately.
5. Delete the bar plot.
6. Create a scatter plot.
7. Move plot to desired position.
8. Move plot to desired position and scale it appropriately.
9. Delete the scatter plot.
10. Create a new scatter plot in front of you.
11. Assign *Sepal Width* to one of spatial axes.
12. Assign *Petal Width* to another spatial axis.
13. Assign *Sepal Length* to the third spatial axis.
14. Assign *Class* to plot's color.
15. Slice the plot to isolate the green cluster using Petal Width.
16. Create a new scatter plot.
17. Load dataset *Abalone*.
18. Assign *Diameter* to one of spatial axes.
19. Assign *Length* to another spatial axis.
20. Assign *Whole weight* to the third spatial axis.
21. Assign *Sex* to plot's color.
22. Assign *Rings* to plot's size.
23. Slice *Whole weight* from 0.8 to 2.0.

After concluding the timed test, participants were given the third and final part of our questionnaire. They were tasked to choose whether they agree with the following statements on a scale from 1 to 5:

- Cyberplot is easier to use than traditional 2D visualization tools.
- I was able to easily grasp information presented to me.
- Moving objects in 3D space felt intuitive.
- The size of the virtual environment felt adequate.
- I perceived benefit in percepting data using Cyberplot compared to using traditional 2D tools.
- The process of getting data from computer to virtual reality felt straightforward.
- Scale labels on plot were legible.
- Changing slice boundaries was easy.
- Free-form rotation felt natural.
- Using Cyberplot felt fun.
- Plot nodes felt three-dimensional.
- I did not encounter issues with controls in VR. (white/3DOF headset)
- I did not encounter issues with controls in VR. (black/6DOF headset)
- Using the plugin system was easy.

An open-ended question followed - "Is there anything you found frustrating about Cyberplot? Are there any features or plugin integrations you would like to see implemented?".

Participants were then asked to rank the following plots in the order of their interest:

- 3D bar plot
- map plot
- parallel coordinate plot
- surface plot
- globe plot

Testing concluded with a standardized Simulator Sickness Questionnaire (SSQ).[1]

#### Findings

One participant out of four did not have any prior experience with virtual reality. ParaView was universally regarded as being hard to use with Tableau being rated 4/5 on average. Out of all interactions, changing slice boundaries was the most problematic, with an average rating of 3/5 on the easiness scale. Timestamps in test reports confirm this fact. There was a large variance in the question regarding the simplicity of our plugin system - participants with no prior programming experience have both given a rating of 2/5. 

When conducting demonstrations of Navigator, participants often had trouble recalling interactions shown in the tutorial video, one participant mentioned this fact in the questionnaire, adding that the videos could be faster. Another participant voiced their frustration with assigning attributes onto non-spatial features of a scatter plot. Exact plot positioning in the timed test also proved challenging, especially when using the analog stick of an Oculus Rift controller.

Overall interest in plots was as follows (1 - most interested):

1. globe plot
2. map plot
3. bar plot
4. surface plot
5. parallel coordinate plot

Participants experienced at worst mild symptoms of motion sickness (with a 50% incidence among those susceptible to motion sickness in VR as per question #2).

### December test

This round of testing took place at Czech Technical University in Prague. Seven participants took part. Based on the experience from our August test, we have redesigned the test schedule in order to reduce the time required for each session. Nevertheless, test sessions took slightly over one hour on average. Hardware-wise, the demo of Virtualitics was conducted on HTC Vive, while Navigator was showcased on Oculus Quest. The schedule was as follows:

1. Questionnaire - section on previous experience.
2. Introduction to data visualization.
3. Showcase of Tableau.
4. Showcase of Virtualitics.
5. Questionnaire - section on traditional tools.
6. Introduction to Cyberplot.
7. Demo of Manager and plugins.
8. Demo of Navigator on Oculus Rift (6DOF).
9. Timed tests incorporating all components.
10. Questionnaire - Cyberplot-specific section.

We have been able to acquire an evaluation version of Virtualitics immersive analytics software, which replaced ParaView in our testing schedule. Demonstration of the 3DOF version of Navigator has been omitted due to time constraints. Emphasis was placed on newly added features, most notably the new plot types and immersive mode.

The first part of our questionnaire was left intact, while the second part substituted ParaView for Virtualitics and now reads as follows:

- Rank ease of use of Tableau. (1-5, where 5 means easy to use)
- Rank ease of use of Virtualitics.

The timed test consisted of the following tasks:

1. Load dataset *Iris*.
2. Create a scatter plot.
3. Assign *Sepal Width* to one of spatial axes.
4. Assign *Petal Width* to another spatial axis.
5. Assign *Sepal Length* to the third spatial axis.
6. Assign *Class* to plot's color.
7. Assign *Class* to label.
8. Rotate the plot.
9. Enter immersive mode.
10. Slice Sepal Width approximately from 0.78 to 1.8.
11. Slice Petal Width approximately from 2.8 to 3.7.
12. Scale the plot.
13. Move about.
14. Exit immersive mode.
15. Load dataset *Population*.
16. Create a globe plot.
17. Assign latitude.
18. Assign longitude.
19. Assign population onto values.
20. Enter immersive mode.
21. Open up the statistics panel.
22. Scale and rotate the globe.
23. Exit immersive mode.
24. Create a surface plot.
25. Load dataset Sombrero.
26. Assign values onto newly created surface plot.
27. Enter immersive mode.
28. Move about.
29. Exit immersive mode.
30. Delete one of the plots.
31. Listen to instructions.
32. Listen to instructions.
33. Listen to instructions.

The last three tasks were more involved and required answering an open-ended question regarding a specific dataset based on observation. As such, they require manual confirmation by the test conductor, which is done by pressing a button on a connected game controller (DualShock 4). The reporting capabilities of our automated testing suite were greatly improved with the addition of action-based logging - please see the appendix for details.

The third part has been updated with newly added features and rephrased as to reduce any possible bias, which the author felt were present in the first version of the questionnaire. Participants were asked to rank their satisfaction with the following:

- Ease of use compared to 2D visualization tools (ex. Tableau)
- Ease of use compared to immersive analytics tools (ex. Virtualitics)
- Intuitiveness of plot positioning in 3D space
- Added benefit in perception of data using Cyberplot compared to traditional 2D tools
- Ease of loading new datasets from a local file (Manager)
- Ease of modifying uploaded datasets (Manager)
- Legibility of text on scales
- Ease of changing slice boundaries
- Navigation inside immersive mode
- Quality of information provided by statistics panel in immersive mode
- Spatial (three-dimensional) feel of plots
- Clarity of iconography, visual design
- Ease of assigning attributes from a data set onto a plot
- Overall ease of use (Navigator)
- Ease of use of the plugin system (Python/R)

An open-ended question then followed with the same phrasing as in the original version of the questionnaire. Afterwards, participants were asked to order plots that have been recently implemented by the level of their interest. A new section has been added, in which participants have to provide a textual description for icons present around the interface. Testing once again concluded with the standardized Simulator Sickness Questionnaire.

#### Findings

This time all of our seven participants have had at least some experience with virtual reality. One of our participants answered that they often suffer from motion sickness in VR, although according to their SSQ results, they did not feel any moderate or severe discomfort, whereas another participant, who does not typically suffer from motion sickness, noted that they suffered from moderate fatigue and blurred vision after using our application. Most of our test participants had at least some experience with programming. There was again correlation between programming experience and perceived ease of use of our plugin system.

The average rating of Tableau was 3.3/5, whereas Virtualitics fared worse at 2.6/5. For comparison, Navigator received a score of 4/5. We partially attribute the suboptimal rating for Virtualitics to the fact that we have used HTC Vive during its demonstration. The reduced comfort of its controller in comparison to Oculus Touch may have resulted in a slight negative bias. One particular point of discomfort with Virtualitics's UI was the lack of clarity in regards to mapping geospatial attributes onto a globe plot, since the software lists spatial axes as X, Y and Z independently on plot type. Navigator's *latitude*, *longitude* and *value* feature descriptions were universally praised in comparison.

Opinion on the ease of use of Navigator in comparison to Tableau were mixed with two participants preferring the more traditional WIMP interface. However, most participants see the added benefit in using immersive tools. The weakest area of Navigator seems to be the newly added immersive mode with navigation inside immersion mode ranked at 2.9/5. Complaints include the lack of ability to rotate the plot without exiting immersive mode and a suboptimal speed of movement, although none of the participants complained about sickness when positioning a plot in immersive mode, no doubt helped by the addition of the static grid that fills the environment when doing so.

Overall interest in plots was as follows (1 - most interested):

1. globe plot
2. map plot
3. scatter plot
4. surface plot
5. bar plot

We can see that the interest in the 3D bar plot fell considerably compared to the first round of testing. One of the participants complained about occlusion present in this particular plot type. We think that adding the ability to slice bar plots could mitigate some of their faults. Globe and map plots were once again voted as the most interesting plot types by participants.

When it comes to iconography, the participants were able to associate most icons with their correct meaning, however there were some outliers. The value icon (three vertical bars) was only recognized in one instance, the arrow sign for vector also proved challenging and will have to be redesigned. Categorical attributes were mostly referred to as *shapes*, corresponding to their association with the glyph feature in scatter plots.

Further criticism included the design of feature labels in plots, which only display after pointing at the graph with a controller and the quality of feedback when selecting an attribute from the data brush. One participant suggested that labels in scatter plots could simultaneously display values from multiple attributes, while another suggested the use of an analog stick to flip between various views inside the statistics panel (*swatch*).

1. (sickness) https://www.researchgate.net/publication/221494074_Simulator_Sickness_in_Mobile_Spatial_Sound_Spaces