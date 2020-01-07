# Introduction

The advances in technology over the past 30 years have brought us treasure troves of data. With the rise of the Internet especially, we are living in a world filled with information. Internet of things, big data and cloud are just some of the buzzwords that are often used in popular media. As the century turned, data had become the new oil. New industries were born out of nowhere as more and more people realized that information is power.

We live in an age where products we use know more about ourselves than we do. Data has been weaponized to change public opinion during the 2016 US presidential elections. Chief executive officer of a consulting company employed by the presidential elect Donald Trump has been quoted as saying that they keep four to five thousand data points on nearly two thirds of US population.[1] This data has been used to classify individuals based on political preferences and for targeted advertising. The Cambridge Analytica dataset is just one example of big data, a popular term that denotes data of high volume, variety (form of data), veracity (uncertainty) and velocity.[2]

However, if we are to gain insight from such data, we have to find effective ways of analyzing it. Data analytics is the process of finding, interpreting and communicating data. Data visualization provides an effective means of communicating the results using visual representations. A related term that is often used interchangeably with-, but is often thought of as a superset of data analytics software, is Business intelligence (BI). BI software incorporate so-called decision support technologies, which include predictive analytics, benchmarking and various kinds of other tools. They utilize special databases that are capable of handling big data.[3]

As we will discuss in the following chapter, these pieces of software are not very user-friendly and are often unavailable for those outside of large corporations due to their reliance on enterprise-focused technology and business models, which make such products unattainable by end consumers. The hypothesis of our work is that we can make data visualization more accessible by utilizing novel interaction techniques, specifically spatial interfaces used in virtual reality (VR) applications. We will also discuss the state of virtual reality in 2019 and implications of using such technology in the context of data visualization before moving on to look at current applications in the area. We will then discuss in detail the design process behind our application and follow up with specification of our testing methodology and evaluation of feedback we have received from test participants. We will also provide a brief description of the technology used in the implementation stage and conclude the thesis with a look into the near future.

## Chapters

The thesis is comprised of the following chapters.

### Motivation

In this chapter we are going to go over several examples of traditional data analytics and business intelligence software, i.e. software that runs on a personal computer and utilizes a flat user interface. We will try to assess the ease of use and come up with reasons why VR might help us in this space.

### Domain analysis

In this chapter, we will analyze the state of virtual reality in 2019 and take a look at a couple examples of applications in the space of immersive analytics. Furthermore, we will define our target group and set design goals to help narrow down our scope.

### Design

In this chapter we will discuss in detail the target user group and use cases of our application, specify important goals that we would like to meet, select features to help us meet these goals and talk about implications of virtual reality prototyping on our design process.

### Manager

This chapter includes description of the prototyping process behind Manager, our web component. We will start by creating wireframes and continue by implementing two versions of the component.

### Plugins

This chapter introduces plugins, programming integrations intended for developers and power users to incorporate dataset creation and updating functionality into their applications and scripts.

### Navigator

This chapter concerns the design and implementation of Navigator, the VR component of our application. The process of design and creation of three prototypes is discussed.

### Testing

In this chapter, we will compare the efficiency of our application against that of its contemporary alternatives introduced in chapter 1, introduce our testing methodology and present some of the findings.

### Used technology

In this chapter we will briefly discuss the technological stack behind our applications suite, which consists of a web component called Manager and a VR application called Navigator. Plugins are omitted, as their implementation varies on the language that they interface with.

1. (cambridge) https://news.sky.com/story/behind-the-scenes-at-donald-trumps-uk-digital-war-room-10626155/
2. (bigdata) https://www.ibmbigdatahub.com/infographic/four-vs-big-data/
3. (bi) https://cacm.acm.org/magazines/2011/8/114953-an-overview-of-business-intelligence-technology/fulltext/