# Used technology

In this chapter we briefly discuss the technological stack behind our application suite, which consists of a web component called Manager and a VR application called Navigator. Plugins are omitted, as their implementation varies on the language that they interface with.

All user data is stored in Manager and is exposed to Navigator using a set of application programming interfaces (API) adhering to the REST (Representational State Transfer) standard.

## Manager

Manager consists of a back end written in Flask, a lightweight web application framework for Python.[1] We make use of a number of Python packages, most notably Numpy[2] and Pandas[3], which allow us to extract statistical information from uploaded datasets, and SQLAlchemy, an object-relational mapper (ORM) that enables developers to easily create and manage database schemas directly in Python.[4] In production, we make use of MySQL database system.[5] Front end is written in Vue.js, a JavaScript framework designed for building reactive single-page applications (SPA).[6]

## Navigator

Navigator has been written in C# using Unity game engine. Unity allows us to deploy on mobile headsets running the Android operating system as well as personal computers running Microsoft Windows, while maintaining a single codebase.

In order to support multiple head-mounted units (HMD), we have to target a number of software development kits (SDK), namely Oculus Utilities (Oculus Go, Quest and Rift)[7], Microsoft Mixed Reality Toolkit (Windows Mixed Reality headsets)[8] and Valve's OpenVR (HTC Vive, Valve Index).[9] While these tools provide some degree of compatibility with headsets from other manufacturers, we have opted to use a wrapper called TButt, which provides abstractions of basic functions for control handling and locomotion, greatly reducing complexity of our code.[10]

SDK incompatibilities have long been a large issue in VR development, however the release of version 1.0 of Khronos Group's OpenXR at SIGGRAPH 2019 conference held in July 2019 signifies a leap in this area by offering a standardized APIs for all HMDs. The specification is supported by all major VR/AR HMD vendors, as well as other stakeholders in the technology space.[11]

Since we use Unity, we have access to a large number of libraries written for .NET ecosystem. In our project we utilize a REST client[12] that allows us to effortlessly interface with Manager's APIs, as well as an adapted version of SQLite-net called SQLite4Unity3d.[13] SQLite, a file-based relational database based on SQL language, is used client-side to store dataset metadata.[14] The aforementioned library was chosen for its support of LINQ, a feature included in modern versions of .NET Framework that allows for easy querying of composite data types.[15]

1. https://palletsprojects.com/p/flask/
2. https://www.numpy.org/
3. https://pandas.pydata.org/
4. https://www.sqlalchemy.org/
5. https://www.mysql.com/
6. https://vuejs.org/
7. https://developer.oculus.com/documentation/unity/latest/concepts/book-unity-gsg/
8. https://github.com/microsoft/MixedRealityToolkit-Unity/
9. https://github.com/ValveSoftware/openvr/
10. https://tbutt.net/
11. https://www.khronos.org/news/press/khronos-releases-openxr-1.0-specification-establishing-a-foundation-for-the-ar-and-vr-ecosystem/
12. https://github.com/proyecto26/RestClient/
13. https://github.com/robertohuertasm/SQLite4Unity3d/
14. https://www.sqlite.org/
15. https://docs.microsoft.com/en-us/dotnet/standard/using-linq/