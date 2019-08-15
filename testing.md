# Testing

This chapter compares the effeciency of our application against that of its contemporary alternatives introduced in chapter 2. It also outlines the testing methodology.

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
| PBPB | Point on the ground and while holding the trigger select the scatter plot icon, then release the trigger | 2.6 |
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

We plan to structure our testing sessions in the following order:

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

Sections 4-5 and 8-9 are going to be conducted in random order in order to mitigate the effects of confounding influences of practice. Participants are to be selected from a diverse range of backgrounds, emphasis is placed on a large variance of experience with virtual reality and the fields of data analysis, statistics and visualization. Timed tests will utilize a modified version of Navigator capable of creating automatic logs and displaying instructions to the user.