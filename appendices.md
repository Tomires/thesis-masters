# Appendices

## Key-stroke level model (KLM)

| Operator | Description | Time (s) |
| --- | --- | --- |
| K | Keystroke or button press. | 0.28[a] |
| P | Pointing to a target on a display with a mouse. | 1.1[b]
| H | Homing the hand(s) on the keyboard or other device. | 0.4 |
| M | Mentally preparing for executing physical actions. | 1.35 |
| B[c] | Clicking a mouse button. | 0.2 |
Excerpt of used operators.[1]

a. Non-secretary typist average (40 words per minute).

b. Average. Varies with distance and target size according to Fitts's Law: t_p = 0.8 + 0.1 * log2(d / s + 0.5) s

c. Not present as a separate action in the original paper. Instead it is included as part of the homing motion.

## Test reports

In addition to questionnaires, we made use of automated user testing environments to help analyze user behaviour within our application. In addition to times measured for each task, generated test reports list actions conducted by the user complete with timestamps. These include the following:

- opening up a dataset,
- spawning a plot of a certain type,
- assignment of attribute onto an axis,
- deassignment of an attribute from a plot axis,
- modification of attribute range,
- flick-based plot rotation,
- entering/leaving immersive mode,
- accessing data brush panel,
- accessing the Swatch (statistics panel) inside immersive mode,
- change of plot scale,
- movement in immersive mode,
- plot deletion

Generated test reports from the second round of testing are available as part of data provided with this thesis.

## Installation guide

In this section we will go over the setup procedures for components provided with this thesis. It is important to note that there are multiple builds available for each component - 1901 (January), 1908 (August) and 1912 (December). Intercompatibility of components from different builds is not guaranteed (i.e. the August build of Navigator may not be compatible with the December build of Manager).

### Navigator

Navigator, the VR component of our application, is provided as a collection of binary files. PC binaries require a computer running the latest version of Microsoft Windows 10 with Oculus software (1908) or SteamVR (1912) installed. Supported headsets include Oculus Rift and Oculus Rift S, December build is also compatible with Windows Mixed Reality via SteamVR. To launch Navigator, open the exe file located in the respective directory. Android binaries require Oculus Go or Oculus Quest standalone headsets with developer mode enabled.[2] These can be sideloaded using Android Debug Bridge and accessed via the Library interface under Unknown Sources.

By default, Navigator tries to connect to the public instance of Manager located at *cyberplot.tomires.eu*. If you would like to connect to a local version of Manager, please edit the */etc/hosts* file on your operating system (on Windows: *C:/Windows/System32/drivers/etc/hosts*). Insert the IP address of the server running Manager in the following format.

```
127.0.0.1 cyberplot.tomires.eu
```

### Manager

Manager, the web component of our application, is provided in the form of source code bundled with an installation script. Functionality has been tested on a clean install of Ubuntu 18.04 LTS. To begin setup, navigate inside the folder and run the provided script as superuser by using the following command:

```
sudo ./install.sh
```

Follow on-screen prompts and then wait for the installation to finish. Manager instance should then be accessible using a standard web browser.

### Plugins

Included are sample integrations for Python and R. Before use, please modify the *DEFAULT_URL* variable or specify the *serverUrl* argument when calling any of the functions. It should point to an IP address or a hostname of a machine running an instance of Manager.

1. (klm) https://dl.acm.org/citation.cfm?doid=358886.358895
2. (godevmode) https://developer.oculus.com/documentation/mobilesdk/latest/concepts/mobile-device-setup-go/