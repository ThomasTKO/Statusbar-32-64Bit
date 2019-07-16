# Statusbar-32-64Bit 
Rename the 32bit!!!!!!!!! ExileServer_system_database_connect.sqf or 64bit!!!!!!!!! ExileServer_system_database_connect.sqf to ExileServer_system_database_connect.sqf and drop the file on Statusbar Folder 

On Statusbar Folder change on statusBar_update.sqf the time _restartTimes	= [0,6,12,18,24]; // Military Time (this its 6H restart)

1# Unpack your mission file 
2# Copy the folder "Custom" from the Zip file to your mission file \Server\mpmissions\Exile.Altis (example). So the path is \Server\mpmission\Exile.Altis\Custom\StatusBar\

3# Add this to initPlayerLocal.sqf
// Load Status Bar [] execVM "Custom\StatusBar\statusBar_init.sqf"; 
///////////////////////////////////////////////////////////////////////////////
// Static Objects
///////////////////////////////////////////////////////////////////////////////
// Load Status Bar
[] execVM "Custom\StatusBar\statusBar_init.sqf";


4# Add this to your description.ext into the class "RscTitles"
#include "Custom\StatusBar\statusBar.hpp" So it should look like this:

class RscTitles 
{     // Status Bar 
      #include "Custom\StatusBar\statusBar.hpp"
}; 
#5 Copy the override file depending on your extdb2 or extdb3 into \Server\mpmissions\Exile.Altis\Overrides\ and add it to the CfgExileCustomCode section in your mission config file ( \Server\mpmissions\Exile.Altis\config.cpp )

//StatusBar 
ExileServer_system_database_connect = "Custom\StatusBar\ExileServer_system_database_connect.sqf";

So it should look like this:

class CfgExileCustomCode { 
//StatusBar
ExileServer_system_database_connect = "Custom\StatusBar\ExileServer_system_database_connect.sqf";
}; 
6# Pack your mission file again and you are done....
