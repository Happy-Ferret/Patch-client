Patch-client
============

Basic binary patch clients for Mac OS X, GNU/Linux and Windows.

###Premise

The goal of this project is to create a quick drop-in update/binary patch solution developers may add to their project.

###Technology

In order to achieve cross-platform compatibility, the basic patch mechanism will be implemented in Haskell code. 

###Mechanics

* The patch-client will first check whether the binary that is about to be patched is still running. Should this be the case, the user will be given the chance to quit the program. 

* Next, the patch-client will check if the currently installed build matches the most recent patchset (information about this can be provided inside two external text files. One stored locally, one on the server)

* Should the local version string not match the one stored on the server, the patch-client will perform the download of the binary patch using a feature similar to wget/curl.

* Once the download is complete, the patch will be applied using a Haskell based re-implementation of bspatch. 

* The user is informed about the success/failure of the patching process. 
