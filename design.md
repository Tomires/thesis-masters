# Design

In this chapter we will discuss the users and use cases of our application, specify important goals that we would like to meet, select features to help us meet these goals and talk about implications of virtual reality prototyping on our design process.

## Personas

The following personas characterize potential users of our application.

### Novice

![](images/persona_frank.jpg)

Frank is a hobbyist. He is capable of performing basic computer operations, such as browsing the Internet or using an office suite. Lately, he came across an interesting dataset that highlights population growth in different areas of the world over the past couple centuries. Frank is quite impatient when it comes to computers and gets easily frustrated with complex pieces of software. As such, he is looking for a tool that will enable him to view this data without too much hassle.

### Power user

![](images/persona_quinn.jpg)

Quinn is a senior data analyst working in meteorological agency. She possesses advanced programming skills and her current task is to build a networked swarm of drones that gather meteorological data from locations around her neighbourhood. She wants to remotely access the measured data and share measurements from particular days with her colleagues.

### IT administrator

![](images/persona_paul.jpg)

Paul works as an IT technician at a corporate bank. He has been tasked by the company to find and recommend an immersive analytics platform to be used by its employees. Paul wants the software to store data locally in order to achieve compliance with new data regulations, integrate easily with existing processes inside the company and have the ability to audit the software. Although he is an experienced administrator with many years under his belt, he always enjoys software that is hassle-free to run and easy to set up.

## Task analysis

The goal of our research is to create a virtual reality visualization environment that is accessible to everyone, is easily extensible by outside developers and works on 3DOF and 6DOF HMDs, no matter whether they are connected to a personal computer or function as standalone devices. Different control styles should be taken into account when designing interactions. The following graph illustrates tasks that are typical for immersive analytics software (and for the most part, traditional business intelligence tools). High-level tasks are broken down into subtasks as is commonplace in hierarchical task analysis.[1]

![Hierarchical task analysis of typical immersive analytics software.](images/hta.pdf)

The users typically traverse these tasks in order, however, depending on the scenario, they may want to repeat tasks 2-4. It is important to note, that when collaborating with another user, tasks 1-2 can be skipped. Detailed description of each task follows.

| Task | Description |
|---|---|
| Prepare data | The user has to define the underlying structure of data they want to use. This is typically a local file in a certain format or an API provided by a third-party application. They can then proceed to retrieve such data and specify various associated feature (*metadata*), such as attribute types or labels (in case of multivariate data). They are also able to select a subset of data to work with or fill in missing values. |
| Map data | The user makes an informed decision on which plot type they wish to use and associates attributes from their dataset with its features. They are also able to conduct plot-specific filtering (e.g. by modifying the range of displayed values on a spatial axis in scatter plots). |
| Analyze data | This task includes looking at plots from different view points and discovering further information by consulting the legend. |
| Collaborate | Collaboration can be divided into two distinct areas - synchronous and asynchronous. If the user we are collaborating with is available for real-time collaboration, we can invite them to a persistent virtual space and communicate using voice and physical gestures that map onto our virtual avatars. Alternatively, we are able to send them a copy of our dataset, which they can analyze at their leisure. |

## Scenarios

Let us specify three scenarios that highlight certain use cases.

### Loading a dataset from a local file

Frank opens up the application, logs in and proceeds to add a new dataset representing population growth in the last century. He locates a CSV file on his computer and answers a series of simple questions. After the application finishes loading the dataset, he promptly checks whether the data has been correctly loaded and attribute types correctly assigned. He notices that several attributes have been mistyped as numerical instead of locational and that several attribute labels are ambiguous. He proceeds to fix these issues and puts on a virtual reality headset.

Inside VR, Frank selects the dataset he had just uploaded and creates a globe plot. He assigns locational attributes onto compatible features of the plot and specifies a numerical attribute as value. As Frank rotates the globe, he observes several hotspots around the world - eastern portions of China catch his eye. He moves the globe closer towards him and continues to explore.

### Creating an integration

Quinn has recently finished work on her new army of internet-connected drones. She is using Python to periodically gather measurements of temperature, humidity, wind direction and wind speed. Every day at a set time, the drones travel along a pre-programmed path and log measurements at certain locations. These measurements are then dumped into a file, which is stored in the drone's internal memory. Quinn, wanting to utilize the full capabilities of her drone, decides to add an integration to her Python script. She opens up our application, logs into her account and adds the file containing her last measurements as a new dataset. She then turns on a feature called *version history*, that enables her to upload multiple versions of the same dataset.

Quinn proceeds to look up the API key specific to the dataset she had just added along with instructions on how to set up the Python integration. After installing the integration from Python's package manager, she replaces the bit of code that saves measured data as a file with a snippet that she found. The next day after her drones return from their travels, Quinn notices that a new version of data has been added to her dataset. She puts on her VR headset, creates a map plot and assigns attributes from her dataset onto its features. Quinn then changes between the two versions and can see that today's measurements indicate higher humidity in certain areas as well as a change in wind direction.

### Collaborating with another user

Quinn wants to share her findings with her fellow employee, Bob. While in VR, she opens her friends list and notices that Bob is online. She invites him to join her in VR. Bob gets a notification and puts on his VR headset. He accepts the invitation and after waiting several seconds for Quinn's data to load, appears in a shared virtual space beside Quinn's virtual avatar. Quinn then briefs Bob about the current meteorological situation using the application's voice communication functionality. She points to the area of interest and both agree that the situation is unusual. Bob requests a personal copy of the dataset and Quinn is happy to oblige. She takes off her VR headset and sends the dataset to Bob who then receives a prompt to accept the share request.

## Design goals

Let us specify key design goals for our application.

### Inclusivity

The application should be accessible to users without any prior experience with data analysis. Workflows that are expected to be utilized by the vast majority of users should be straightforward. More advanced functionality can be available for experienced users, but its presence should not deter newcomers from using the product.

### Extensibility

The application has to be extensible to a certain degree as to give stakeholders the ability to integrate it with their existing software stack.

### Data security

Users are not to be held hostage inside the application's ecosystem (*vendor lock*). All data should be retrievable with ease by the user and a system administrator where applicable. There should be an option to store data locally without a requirement to connect to outside servers.

### Collaboration

The application should facilitate collaboration between multiple users. They should be able to share data with one another without being forced to resort to external tools. In an optimal scenario, they should have the ability to communicate and interact with one another inside the virtual environment.

### Non-specificity

Use cases of our application should not be limited to a select field or domain of data.

### VR

The application's user interface should be tailor-made for virtual reality. It is to be designed around a spatial environment while mitigating all shortcomings of present-day virtual reality technology.

### Availability

The application is to be available on all major virtual reality platforms across PC, mobile and standalone categories. The user should be able to retain a persistent copy of their data across all devices as they may for instance use a workstation at their workplace and a standalone system at home.

### Automatization

When adding a new dataset, the application should be able to predict certain features, such as attribute type or structure of an uploaded dataset. The user should only be prompted if there is a high degree of uncertainity. In the inverse case, we will choose the most likely settings and allow the user to make modifications later at their leisure.

## Feature selection

**REVISE**

We have selected a number of features to implement for our first prototype, which was made in the space of 4 months (one academic semester). These include the ability to load comma-delimited CSV files into the environment, ability to update existing datasets by either overwriting the existing copy or appending a new copy (*versioning*), letting the user perform basic editing operations such as renaming dataset attributes, setting their data type and missing value setting and a basic dataset sharing feature.

The user should also be able to create various types of plots, position them freely around the virtual environment, adjust their rotation and scale, specify bounds for each spatial axis (*slicing*), assign dataset attributes onto spatial axes and non-spatial features such as color and size and view basic dataset metadata and statistics of attributes contained within said dataset.

Lastly, there should be integration support for popular programming languages that allows programmers to create or update datasets from their programming environment of choice. Since we cannot cater to all, we should provide the ability for outside developers to build their own integrations for other programming languages or environments.

### Plot types

**XX**

### Attribute types

## Component design

**EXPAND**

We have decided to divide our environment into three distinct components - plugins, Manager and Navigator. *Plugins* are API integrations written for different programming languages that allow the user to create a new dataset or update an existing one. *Manager* enables the user to view and edit all of their datasets and also facilitates uploading files from a local computer. *Navigator* allows the user to interact with their data in virtual reality. The following visualization pipeline shows the distribution of tasks among our components.

![Adapted version of Haber–McNabb dataflow model for scientific visualization in the context of our environment.](images/pipeline.pdf)[2]

## Challenges of designing VR applications

The spatial nature of virtual reality applications carries with it certain design challenges, which make it difficult to utilize the typical prototyping workflow. As interaction techniques in VR are infinitely more complex than in typical WIMP applications, we are unable to create a rich interactive prototype without delving into code.

1. (hta) https://www.uxmatters.com/mt/archives/2010/02/hierarchical-task-analysis.php
2. (santos) https://www.sciencedirect.com/science/article/pii/S0097849304000251/