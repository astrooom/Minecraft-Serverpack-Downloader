# Curseforge Serverpack Downloader and Installer

This is a script made to automatically download and install Minecraft modpacks from 
<a href="https://curseforge.com">Curseforge</a> as intended by the modpack author. Serverpacks provided for modpacks by their authors come in very different kinds, with many different installers. This is an attempt to unify the installation of all serverpacks (for both Forge and Fabric) as the modpack author intended them to be.
The script will:
1. Download the modpacks author-provided serverpack from the Curseforge Project ID (works with either the latest modpack version or a specified one - see below)

2. Run any provided installers through a unification attempt that come with the serverpack if needed.

3. Remove garbage files.

## How to use
### 1. Download and unarchive the repository into any directory

### 2. Run "run.py" with required arguments like:
python run.py ```mode``` ```modpack_id``` ```modpack_version``` ```clean_startup_script```
#### Required arguments
##### ```mode```
Available modes: ```normal``` and ```pterodactyl```
Normal is intended to use locally on your PC. Pterodactyl is intended to use in conjunction with a pterodactyl egg install script. If you do not know what this means, use ```normal```.
##### ```modpack_id```
This is the modpacks project ID found on <a href="https://www.curseforge.com/minecraft/modpacks">the Curseforge website</a> in the top right "About Project" section of your desired modpack.
##### ```modpack_version```
Which version of the modpack to install. Specify a version from the modpacks name. For example, <a href="https://www.curseforge.com/minecraft/modpacks/rlcraft">RLCraft</a> names their releases like "v.2.9", "v.2.8.2" etc (as you can see by going to the "Files" section). Here, you could type "v.2.8.2" to pull that version. Use ```latest``` to pull the latest serverpack if exists. In conjunction with Curseforges' release type system, ```latest``` will always to try to pull the latest "recommended" serverpack from Curse. If no "recommended" version exists, it will pull the latest "beta" serverpack. If no "beta" version exists it will pull the latest "alpha" serverpack. If the modpack has no provided serverpack at all it will pull the latest non-serverpack in the same order.
##### ```clean_startup_script```
Use ```True``` (must be capitalized) to clean provided "run.bat" and "run.sh" / "start.bat" and "start.sh" (or any other name they may have) server startup script files after installing the server. Use ```False``` to keep them.