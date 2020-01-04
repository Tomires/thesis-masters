# Domain analysis

In this chapter, we will analyze the state of virtual reality in 2019 and take a look at a couple examples of applications in the space of immersive analytics. Furthermore, we will define our target group and set design goals to help narrow down our scope.

## Target group

Our application should provide an intuitive way to view data in a virtual reality environment in an attempt to leverage the spatial properties and immersion. It should be friendly enough to be accessible to users with basic computer skills while also providing advanced functionality to power users via API integrations.

## Target platform

In order to specify a baseline for our application, we first need to look at the current landscape of virtual reality hardware. Over the years, we have primarily been dividing virtual reality systems into two main categories - phone- and PC-based VR. The former category includes ecosystems like Google Cardboard[1] and Daydream[2] and Samsung's GearVR[3], while the latter includes three primary vendors - Oculus with its Rift headset[4], Microsoft's Windows Mixed Reality[5] ecosystem composed of head-mounted displays (HMDs) made by third-party manufacturers and Valve's SteamVR[6], which includes support for pretty much any PC-based headset.

![Examples of various contemporary virtual reality systems. Clockwise from top: Google Daydream View (mobile), HTC Vive (PC), Oculus Quest (standalone), Google Cardboard (mobile)](images/hmd_examples.png)

There are two primary differences between the two mentioned categories. The first concerns system resources available to developer. Graphics processing units (GPUs) in modern personal computers are significantly more powerful than their handheld counterparts and as such, software can be ran at much higher fidelity. To get a rough idea on performance targets for PC and mobile, we can consult Oculus' development documentation. The recommended limit for draw calls and vertices is 100 and 100,000 for mobile and 1,000 and 2,000,000 for PC, more than a ten-fold difference.[7] We also have to keep in mind that this number is based on minimum requirements for Oculus Rift headset, which mention an Nvidia GeForce GTX 1050 Ti GPU.[8]

The second difference has to do with capabilities in regards to sensing movement and rotation of controllers and the HMD itself. Mobile headsets are limited to 3 degrees of freedom (DOF), making use of rotational data from the phone's inertial measurement unit (IMU), whereas PC-based systems generally offer 6 degrees of freedom (6DOF), which enables developers to utilize position as well as rotation. Controllers typically offer an array of buttons, digital/analog triggers and either a thumbstick or touchpad. The most basic VR systems do not offer a controller at all (Google Cardboard) or a non-tracked controller (also referred to as 0DOF, early iterations of Oculus Rift). These systems are restricted to gaze-based interaction techniques such as *dwell selection*, where an action is triggered by lining up a reticle at the center of a screen with an object and keeping the head still for a defined period of time.[9, p. 328]

![Left: Oculus Go controller offering 3 degrees of freedom. Right: Oculus Touch 6DOF controller.](images/dof_explanation.png)[10]

The last two years saw a shift from phone-based VR into a completely new category of standalone virtual reality hardware, composed of headsets like Oculus Quest[11], Oculus Go[12] and HTC Vive Focus[13]. These headsets offer a much better end-user experience and reduce barrier to entry by removing the need for a powerful enthusiast computer or a compatible smartphone. Technical capabilities of these devices are somewhere inbetween the two traditional categories with devices like Oculus Quest offering 6DOF inside-out tracking capabilities and ability to run graphically optimized versions of content previously exclusive to PCs.

In order to start designing our application, we first have to decide on baseline hardware as all future design decisions have to take into consideration techical limitations of targetted devices. In order to support the largest possible userbase, we aim to support all classes of VR systems. To keep development manageable, we will primarily target Oculus hardware. We have chosen this particular company as it encompasses all three categories (PC, mobile, standalone) with its devices. The only ecosystems we will not support are Google Cardboard due to lack of hand controllers (and thus the necessity of designing around gaze-based interaction methods) and Google Daydream due to the recent discontinuation of the platform.[14]

## State of the art

In this part we will focus on analyzing existing VR-enabled visualization tools. Emphasis is given on select features that author perceives as relevant. We will explore data support to see how we can load data onto the platform, as well as options for extensibility via plugins. Due to the rise of mobile HMDs, we will look at how well they are supported in each product. From the feature set, we will focus on machine learning capabilities and collaboration features. Lastly, we will take a quick look at business models of companies that develop these applications and check availability of editions aimed at end consumers and/or academia.

### Virtualitics

Virtualitics aims to combine the benefits of high-dimensional visualization in VR with those of AI-driven analysis.[15] Virtualitics includes a Windows application for loading, editing and visualizing data in both desktop mode and VR, the later enables the user to visualize data in an immersive environment as well as to collaborate with other users who are represented as avatars. Virtualitics also offers a Python API, which enables programmers to implement an integration into their applications. This API is available in the Python repository under a FOSS license (MIT).[16]

![Spreadsheet view in Virtualitics's desktop application.](images/virtualitics_spreadsheet.png)[17]

The interface of Virtualitics's desktop application bears resemblance to Tableau. Data can be loaded from either a local file or a remote database. It includes a *spreadsheet view*, which shows loaded data in a tabular form with histograms and basic statistical information such as mean and median. The user is able to filter data and fill in missing values.

Afterwards, they are able to switch into the *mapping view*, which allows them to map attributes onto dimensions. A unique feature called *smart mapping* offers the user a selection of attributes that are calculated to be the most important in the dataset. The user can also toggle between multiple plot types.

![Mapping view in Virtualitics's desktop application.](images/virtualitics_mapping.png)[17]

The VR component dubbed *Virtual Office* allows the user to interact with plots they have defined in the *mapping view* in VR. They are able to access key features of the desktop application using flat panels which look the same as they do in desktop mode. The user can interact with one 3D plot at a time, which is located at the center of the virtual space with 2D plots surrounding the user and offering more insight. The software includes a collaboration feature, enabling the user to invite other stakeholders into their virtual environment.

Virtualitics's Python API enables the user to connect to a running instance of the desktop application and load data from a Pandas data table as well as access certain analytics and visualization features straight from their code.

![Virtualitics's VR interface.](images/virtualitics_vr.png)[17]

Virtualitics includes support for Oculus Quest, however it is interesting to note that due to limited hardware capabilities, arbitrary limits are in place for dataset size and number of points rendered in plots. If the limit of points is reached, the software renders them as 2D billboards rather than as meshes.[18]

Out of the three products that we have analyzed, Virtualitics seems to be the most advanced. It offers a very clean task-driven user interface, powerful tools for analytics, mobile support for Oculus Quest, large number of integrations with an open-source Python API and collaboration features. Negatives include proprietary nature of all other components, which require users to resort to the aforementioned Python API, lack of support for 3DOF headsets such as Oculus Go or Google Daydream, VR interface that is perhaps too similar to its desktop counterpart and does not fully utilize the capabilities of room scale VR and, as with all other products mentioned, lack of any consumer or academic version.

### LookVR

LookVR is a virtual reality tool for exploring data that is part of Looker, an enterprise business analytics platform.[19] Looker enables its customers to connect to more than 50 types of databases. Their BI platform can be accessed via a web browser, a demo of an example dashboard is available.[20] LookVR enables the user to access 3D scatter plots, bar plots as well as more unorthodox plot types hosted on Looker. There does not seem to be any interactivity at all outside of selecting a plot. The software allows the user to push a cartoon-like *big data* button in order to enlarge the visualized plot.

![LookVR's user interface.](images/lookvr.png)[21]

LookVR is available for free via Steam.[21] If the user's company has access to Looker, they may log in using their credentials, otherwise a small selection of plots is available as a sample. Unfortunately, all of our attempts to load sample data have ended unsuccessfully.

When it comes to LookVR's feature set, it is rather basic. The amount of available plot types is small, there is no support for mobile HMDs, no extensibility or FOSS components and although it is distributed for free via Steam, the requirement of a Looker license does not allow non-enterprise customers to utilize the product.

### 3Data

Austin-based startup 3Data started as a 2016 prototype called DataVizVR.[22] As of August 2019, this demo is still available via Oculus Store. The demo features a number of preloaded datasets and enables the user to interact with a single plot via a very spartan user interface. Since then, the product has matured, offering various plot types including terrain maps.[23]

![3Data's immersive VR environment.](images/3data.png)[24]

Its user interface, dubbed *3Data Operations Center*, seems similar to Virtualitics with a plot front and center and details surrounding the user in a virtual room, albeit slightly less polished. Like its competitor, 3Data also offers collaboration features.

The product is sold solely to companies as an applications suite called *3Data Power Office*, which in addition to the VR viewer includes tools for creating immersive presentations and collaboration with other stakeholders. Datasets can be self-hosted, 3Data promises direct connection to databases and existing BI tools.[25]

A defining feature of 3Data is its ability to run across multiple classes of devices. The visualization component makes use of WebVR specification, which enables it to run on VR/AR headsets, handheld mobile devices and personal computers in both 2D and immersive modes.[26] 3Data does not seem to offer a dataset editing tool of its own, relying instead on third-party applications.

At the moment, the product does not support any analytical features, however support for *IBM Watson* is coming soon. After a detailed inspection, we concluded that there are no FOSS components whatsoever.

### Summary

Unfortunately, due to the enterprise nature of analyzed products and lack of a consumer/academic license or trial version, we have not been able to test these applications ourselves. The following chart compares key features of analyzed products.

| | Virtualitics | LookVR | 3Data |
|---|---|---|---|
| Data platform support | Local file, database, Python API, Amazon Redshift | Looker | Database |
| Mobile HMD support | Oculus Quest | None | Go + Quest |
| Extensibility / FOSS | Python API | None | None |
| Machine learning | Clustering, Anomaly detection, PCA, *Smart mapping* | Indirectly through Looker platform | Soon (IBM Watson) |
| Telepresence | Yes | Yes | Yes |
| Consumer version | No | No | No |

1. (cardboard) https://arvr.google.com/cardboard/
2. (daydream) https://arvr.google.com/daydream/
3. (gearvr) https://www.oculus.com/gear-vr/
4. (rift) https://www.oculus.com/rift-s/
5. (wmr) https://www.microsoft.com/en-us/windows/windows-mixed-reality
6. (steamvr) https://store.steampowered.com/steamvr
7. (oculusperftargets) https://developer.oculus.com/documentation/unity/latest/concepts/unity-perf/
8. (riftspecs) https://support.oculus.com/248749509016567/
9. (bookofvr) https://www.amazon.com/VR-Book-Human-Centered-Virtual-Reality/dp/1970001127
10. (dofexplanation) https://www.moguravr.com/irasutoya-vr/
11. (quest) https://www.oculus.com/quest/
12. (go) https://www.oculus.com/go/
13. (vivefocus) https://enterprise.vive.com/eu/product/vive-focus/
14. (daydreameol) https://www.theverge.com/2019/10/15/20915609/google-pixel-4-no-daydream-support-view-vr-headset-discontinued
15. (virtualitics) https://www.virtualitics.com/
16. (pyvip) https://pypi.org/project/pyVIP/
17. (virtualiticsvideo) https://www.youtube.com/watch?v=p58Lysfv4FY
18. (virtualiticsquest) https://docs.virtualitics.com/getting-started/oculus-quest-setup-and-installation/
19. (lookvr) https://looker.com/platform/blocks/embedded/lookvr/
20. (lookerdash) https://looker.com/demo/looker-dashboard/
21. (lookvrsteam) https://store.steampowered.com/app/595490/LookVR/
22. (datavizvroculus) https://www.oculus.com/experiences/rift/1251660221572429/
23. (3data) https://3data.io/
24. (3datavideo) https://www.youtube.com/watch?v=9hd_YmYyGQk
25. (3datasuite) https://3data.io/poweroffice/
26. (webvr) https://webvr.info/