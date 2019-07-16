# Statusbar-32-64Bit


1# Unpack your mission file 2# Copy the folder "Custom" from the Zip file to your mission file \Server\mpmissions\Exile.Altis (example). So the path is \Server\mpmission\Exile.Altis\Custom\StatusBar\

3# Add this to initPlayerLocal.sqf

// Load Status Bar [] execVM "Custom\StatusBar\statusBar_init.sqf"; 4# Add this to your description.ext into the class "RscTitles"

#include "Custom\StatusBar\statusBar.hpp" So it should look like this:

class RscTitles { // Status Bar #include "Custom\StatusBar\statusBar.hpp" }; #5 Copy the override file depending on your extdb2 or extdb3 into \Server\mpmissions\Exile.Altis\Overrides\ and add it to the CfgExileCustomCode section in your mission config file ( \Server\mpmissions\Exile.Altis\config.cpp )

//StatusBar ExileServer_system_database_connect = "Custom\StatusBar\ExileServer_system_database_connect.sqf";

So it should look like this:

class CfgExileCustomCode { /* You can overwrite every single file of our code without touching it. To do that, add the function name you want to overwrite plus the path to your custom file here. If you wonder how this works, have a look at our bootstrap/fn_preInit.sqf function.

	Simply add the following scheme here:

	<Function Name of Exile> = "<New File Name>";

	Example:

	ExileClient_util_fusRoDah = "myaddon\myfunction.sqf";
*/

//StatusBar
ExileServer_system_database_connect = "Custom\StatusBar\ExileServer_system_database_connect.sqf";
}; 6# Pack your mission file again and you are done....
