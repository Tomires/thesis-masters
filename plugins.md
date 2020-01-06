# Plugins

Plugins are intended for developers or power users to incorporate dataset creation and updating functionality into their applications and scripts. We have implemented integrations for Python and R, as they are the most common programming languages used by data scientists. Manager provides a set of APIs that enable outside developers to create their own integrations and as both Manager and official plugins are open-source[1], it is a very straightforward process.

![Guide for adding a dataset using Python.](images/manager_python.png)

From the user's perspective, the workflow to add or update a dataset is as follows:

1. Log into Manager.
2. Access the create/update dataset modal.
3. Select programming language or environment.
4. Copy API key that is unique for user (when creating a dataset) or dataset (when updating an existing dataset).
5. Import a library in the programming environment of choice.
6. Insert an applicable command.
7. Run your program.

The following code snippet showcases the use of plugins for adding a new dataset and updating an existing one in R.

```r
cyberplot.new(swiss, id = "304a87cff875bc23522557e5beda11ff", name = "Swiss Dataset")
cyberplot.update(iris3, id = "09fee44cff6a79cdf2a6176b2ffb1008")
```

The December update adds an option to upload compatible data in the form of matrix datasets by specifying an optional parameter. This opens up the possibility for visualizing mathematical functions using surface plots by first creating their discrete approximations and uploading them as a spatial dataset.

```r
cyberplot.new(data, id = "304a87cff875bc23522557e5beda11ff", name = "Matrix dataset", matrix = TRUE)
```

1. (github) https://github.com/cyberplot/