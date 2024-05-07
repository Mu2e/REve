# REve
Eve-7 based event display for Mu2e. Eve-7 (formally REve) is an updated version of the well-known and widely used TEve ROOT based Event Visualization Software. The purpose is to update the TEve code, REve uses modernized infrastcutrue and allows Web Access for remote use.

For more information about Eve-7 and the implementation for Mu2e see: https://mu2ewiki.fnal.gov/wiki/Eve7EventDisplay#Examples_of_the_Eve-7_Mu2e_Display.

# Run an Example

You can run the REve Mu2e code in the same way as any analyzer in Mu2e Offline. 

A number of "examples" are contained in the "examples" directory. The nominal_example.fcl is used for displaying reconstructed (and true MC) for nominal geometry:

```
mu2e -c REve/examples/nominal_example.fcl FILENAME.art  
```

Things can be added and removed on the GUI once set to "true" in the FCL. Just uncheck the boxes associated with the geometry you want to remove.

NOTE: you should run this from your working directory, not inside of REve. This is for the firefox browser path #FIXME.

For extracted position data/MC please use the extracted_example.fcl

# Go to an Event

Currently we have disabled GUI "go to any event" functionality. To filter events use the fcl files labelled "select_event....fcl".

# The GDML

Recently we upgraded the code to use the newest GDML. To get this built you need to run 

```
muse build GDML

```
# The Browser

The user is advised to add the following to their .rootrc:

```
WebEve.DisableShow:   0
WebGui.HttpPort:   01234
```
The first line enables the forefox window pop up on the Mu2e machines IGNORE THAT DISPLAY AND USE YOUR LOCAL BROWSER. The second line sets port number to 1234, this can then be used in your local machine. Assuming you have access to the Fermilab network (either on site or using VPN):

```
mu2egpvm01.fnal.gov:01234/win1/

```

Or create a ssh tunnel:
```
ssh  -Y  -A -L 01234:localhost:01234 sophie@mu2egpvm01.fnal.gov


```

You can then view the display on your local machine without need to use a VNC. Be sure to kill the process on the Mu2e machines when finished to avoid future issues.

# Development

This code is still under development by the Mu2e Analysis Tools Group: Sophie Middleton, Andy Edmonds and Namitha Chitraseemadam. Please contact us to contribute.
