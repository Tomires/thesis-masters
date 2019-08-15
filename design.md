# Design

In this chapter we discuss the structure of our application suite, some key features and go over certain technical and design challenges we had to overcome.

## Feature selection

We have selected a number of features to implement for our first prototype, which was made in the space of 4 months (one academic semester). These include the ability to load comma-delimited csv files into the environment, ability to update existing datasets by either overwriting the existing copy or appending a new copy (*version*), letting the user perform basic editing operations such as renaming dataset attributes, setting their data type and missing values setting and a basic dataset sharing feature.

The user should also be able to create scatter plots, position them freely around the virtual environment, adjust their rotation and scale, specify bounds for each spatial axis (*slicing*), assign dataset attributes onto spatial axes and non-spatial features such as color and size and view basic dataset metadata and statistics of attributes contained within said dataset.

Lastly, there should be integration support for popular programming languages that allows programmers to create or update datasets from their programming environment of choice. Since we cannot cater to all, we should provide the ability for outside developers to build their own integrations for other programming languages or environments.

## Component design

## Components

### Plugins

### Manager

### Navigator