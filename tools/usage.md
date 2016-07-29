#PowerBI Visual Tools (pbiviz) - Usage Guide

The easiest way to create custom visuals is by using the PowerBI command line tools which can be easily to installed via NPM. The command line tools provide everything you need to develop visuals and test them in live PowerBI reports and dashboards. 

**Features:**

* Visual project generation
* TypeScript compilation
* Less compilation
* Automatic live reload
* pbiviz packaging (for distribution)

##Creating a new visual

You can create a new visual project with a single command.

```
pbiviz new My Visual Name
```

Replace "My Visual Name" with the name of your visual. You can change this later by modifying the generated `pbiviz.json` file.

This command will create a new folder in your current directory and generate a basic starter template for your visual. Once it finishes you can open the directory and use your favorite editor to start working on your new visual.

[Learn more about writing custom visuals](../Readme.md) 

-----------

##Testing your visual in PowerBI

You can easily test your visual live in reports and dashboards in the PowerBI service

####Running your visual

To run your visual navigate to the root of your visual project (the directory containing `pbiviz.json`) and type `pbiviz start` to build and serve the visual.

![](images/pbivizStart.png)

This command will compile your [typescript](http://www.typescriptlang.org/) and [less](http://lesscss.org/) files and bundle them for testing. It also launches an https server that will serve your visual for testing in your favorite web browser.

####Viewing your visual in PowerBI
To view your visual, go to your desired report and add the debug visual.  
![](images/debugVisual.png)

Once your server is started, you will see the default template as your visual.
![](images/portalEnable4.png) 

####Toolbar icons (left to right)

* **Refresh Visual** - Manually the visual (if auto reload is off)
* **Toggle Auto Reload** - When turned on the visual will automatically update every time you save a file
* **Show DataViews** - Shows the visual's underlying dataview for debugging 
* **Get Help** - Links to this documentation
* **Send Feedback** - We're always trying to improve the experience so let us know about yours 

-----------

##Packaging your Visual for distribution

Before you can load your visual into [PowerBI Desktop](https://powerbi.microsoft.com/en-us/desktop/) or share it with the community in the [PowerBI Visual Gallery](https://visuals.powerbi.com) you'll need to generate a `pbiviz` file.

To package your visual navigate to the root of your visual project (the directory containing `pbiviz.json`) and use the following command to generate a pbiviz file.

```
pbiviz package
```

This command will create a pbiviz file in the `dist/` directory of your visual project. If there is already a pbiviz file (from previous package operations) it will be overwritten.

-----------

##Troubleshooting 


####Pbiviz command not found (or similar errors)

If you run `pbiviz` in your terminal / command line you should see the help screen. If not it is not installed correctly.

More Info: [Installation Guide](README.md)


####Cannot find debug visual

The debug visual should be the last icon in the visualizations pane (right side) of the report view. If you don't see it ensure you've enabled it in settings.

**NOTE:** The debug visual is currently only available in the PowerBI Service (not in desktop or mobile). The packaged visuals will still work everywhere.

More Info: [How to enable the developer visual in PowerBI](DebugVisualSetup.md)


####Can't contact visual server

Run the visual server by typing `pbiviz start` in terminal / command line from the root of your visual project (see above)

If your server is already running it's likely your SSL certificates weren't installed correctly.

More Info: [How to install the local SSL certificates](CertificateSetup.md)
