# SkyNoonMapManager
Modding tool for Sky Noon that autogenerates .pak files to add modded maps to the in-game map selector. 

Check out the Sky Noon Modding Hub on [Discord](https://discord.gg/svVM2JXJ3G) and [GameBanana](https://gamebanana.com/games/19890). 

# Client Usage
1. Download the latest release of SkyNoonMapManager from the releases tab.
2. Find your Sky Noon installation folder. On Steam, right click Sky Noon > Properties > Installed Files > Browse
3. Navigate to your .paks folder. From the installation folder, go SkyNoon > Content > Paks
4. Drop the SkyNoonMapManager zip folder into the Paks folder. Extract it, then move the executables/dlls from the extracted folder to the base of the paks folder.

SkyNoonMapManager is now ready for usage. Any time you install a new map mod, double click on SNMapManager.exe and it will generate an updated .pak file with a patched map selector.

If you have issues/errors, SNMapManager will output helpful info to the command line which you can send to me with a github issue.

# Modder Usage
Steps for making your map mod compatible with SkyNoonMapManager. SkyNoonMapManager recursively iterates through files/directories in the game's Paks folder, looking for .txt files. A single map entry can be represented as one line in a .txt file, with the following format:

gamemode|name|filename|thumbfilename|loadfilename

- gamemode - must be one of the following: "FFA" "CART" "KOTH" "TDM" "MB" (with no quotes, caps sensitive). Represents the gamemode the map entry should be added to
- name - Display name of the map.
- filename - Filename of the map. When packing your mod, the .umap file MUST be placed in SkyNoon/Content/Maps/ for the game to load it, you should NOT include this filepath in the filename argument.
- thumbfilename - Optional. Filename of the map thumbnail. When packing your mod, your thumbnail .uasset MUST be placed in SkyNoon/Content/Textures/UI/ for the game to load it, do not include the filepath in the thumbfilename argument.
- loadfilename - Optional. Filename of the map loadscreen image. Same restrictions as thumbfilename

You can include more than one map at a time in a text file assuming the map entries are separated on different lines. Example.txt has a showcase of what a typical map txt file with multiple entries should look like. When zipping or submitting your mod, include your .txt file alongside your mod .pak. Name it something unique based on your mod.
