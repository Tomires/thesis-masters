# Used technology

In this chapter we briefly discuss the technological stack behind our application suite, which consists of a web component called Manager and a VR application called Navigator. Plugins are omitted, as their implementation varies on the language that they interface with.

All user data is stored in Manager and is exposed to Navigator using a set of application programming interfaces (API) adhering to the REST (Representational State Transfer) standard.[1]

## Manager

Manager consists of a back end written in Flask, a lightweight web application framework for Python.[2] We make use of a number of Python packages, most notably Numpy[3] and Pandas[4], which allow us to extract statistical information from uploaded datasets, and SQLAlchemy, an object-relational mapper (ORM) that enables developers to easily create and manage database schemas directly in Python.[5] In production, we make use of MySQL database system.[6] Front end is written in Vue.js, a JavaScript framework designed for building reactive single-page applications (SPA).[7]

## Navigator

Navigator has been written in C# using Unity game engine. Unity allows us to deploy on mobile headsets running the Android operating system as well as personal computers running Microsoft Windows, while maintaining a single codebase.

In order to support multiple head-mounted units (HMD), we have to target a number of software development kits (SDK), namely Oculus Utilities (Oculus Go, Quest and Rift)[8], Microsoft Mixed Reality Toolkit (Windows Mixed Reality headsets)[9] and Valve's OpenVR (HTC Vive, Valve Index).[10] While these tools provide some degree of compatibility with headsets from other manufacturers, we have opted to use a wrapper called TButt, which provides abstractions of basic functions for controlling handling and locomotion, greatly reducing complexity of our code.[11]

SDK incompatibilities have long been a large issue in VR development, however the release of version 1.0 of Khronos Group's OpenXR at SIGGRAPH 2019 conference held in July 2019 signifies a leap in this area by offering standardized APIs for all HMDs. The specification is supported by all major VR/AR HMD vendors, as well as other stakeholders in the technology space.[12]

Since we use Unity, we have access to a large number of libraries written for .NET ecosystem. In our project we utilize a REST client[13] that allows us to effortlessly interface with Manager's APIs, as well as an adapted version of SQLite-net called SQLite4Unity3d.[14] SQLite, a file-based relational database based on SQL language, is used client-side to store dataset metadata.[15] The aforementioned library was chosen for its support of LINQ, a feature included in modern versions of .NET Framework that allows for easy querying of composite data types.[16]

1. (fielding) https://dl.acm.org/citation.cfm?id=932295
2. (flask) https://palletsprojects.com/p/flask/
3. (numpy) https://www.numpy.org/
4. (pandas) https://pandas.pydata.org/
5. (sqlalchemy) https://www.sqlalchemy.org/
6. (mysql) https://www.mysql.com/
7. (vuejs) https://vuejs.org/
8. (oculusunity) https://developer.oculus.com/documentation/unity/latest/concepts/book-unity-gsg/
9. (mrtk) https://github.com/microsoft/MixedRealityToolkit-Unity/
10. (openvr) https://github.com/ValveSoftware/openvr/
11. (tbutt) https://tbutt.net/
12. (openxr) https://www.khronos.org/news/press/khronos-releases-openxr-1.0-specification-establishing-a-foundation-for-the-ar-and-vr-ecosystem/
13. (restclient) https://github.com/proyecto26/RestClient/
14. (sqliteunity) https://github.com/robertohuertasm/SQLite4Unity3d/
15. (sqlite) https://www.sqlite.org/
16. (linq) https://docs.microsoft.com/en-us/dotnet/standard/using-linq/