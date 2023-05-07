# dock-fixer
This project contains a Mac OS X application that allows users to solve common issues in the operating system, including problems with the Dock, icons, and the "App Exposé" command. The app is easy to use and customizable with a personalized icon. Ideal for users who want to solve their Mac problems quickly and without using the Terminal.

Steps to create/compile this project

Create an empty folder on your desktop and name it "DockFix.app". This folder will be the resulting Mac OS X application.

Open Terminal and navigate to the "DockFix.app" folder using the command cd ~/Desktop/DockFix.app.

Create a new folder called "Contents" inside the "DockFix.app" folder using the command mkdir Contents. This folder contains all the necessary files for the application.

Create the following folders inside the "Contents" folder:

A folder called "MacOS" using the command mkdir Contents/MacOS. This folder contains the executable file of the application.
A folder called "Resources" using the command mkdir Contents/Resources. This folder contains all the resource files for the application, such as icons and configuration files.
Create a configuration file called "Info.plist" inside the "Contents" folder. This file contains information about the application, such as its name, identifier, and version. Copy and paste the following code into a new text file and save it as "Info.plist" in the "Contents" folder:

arduino
Copy code
{
    "CFBundleGetInfoString" = "DockFix";
    "CFBundleExecutable" = "killdock.sh";
    "CFBundleIdentifier" = "com.yourcompany.DockFix";
    "CFBundleName" = "DockFix";
    "CFBundleIconFile" = "dock_icon.icns";
    "CFBundleShortVersionString" = "1.0";
    "CFBundleVersion" = "1.0";
    "CFBundlePackageType" = "APPL";
}
The information in this file will be used to provide information about the application, including its name, identifier, and version.

Create a shell script file called "killdock.sh" inside the "MacOS" folder. This file contains the code that will be executed when the application is opened. Copy and paste the following code into a new text file and save it as "killdock.sh" in the "MacOS" folder. This file contains the "killall Dock" command that kills the Dock process.
bash
Copy code
#!/bin/bash
killall Dock
This file contains the code that will be executed when the application is opened. In this case, the file contains the "killall Dock" command that will kill the Dock process.

Ensure that the "killdock.sh" file has executable permissions using the command chmod +x Contents/MacOS/killdock.sh.

Copy the icon file "dock_icon.icns" into the "Resources" folder. This file is the icon that will be displayed in the Mac OS X Dock.

Change the permissions of the "DockFix.app" folder using the command chmod -R 755 DockFix.app. This will ensure that the correct permissions are set for the files inside the folder.
