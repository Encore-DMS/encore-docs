# Release Instructions

Encore does not currently have an automated release system. These release instructions have been created in order to avoid mistakes while making a release.

## Instructions

### Build the UI app package
1. Pull the latest encore-matlab-ui repository changes and ensure everything is up-to-date by running: `git pull; git submodule foreach --recursive "(git checkout master; git pull)"; git status`
1. Open MATLAB
1. Change directory to the root encore-matlab-ui submodule directory within the encore-matlab repository
1. Add the lib and src directory and their child directories to the MATLAB path
1. Open Encore UI.prj
1. Click "Refresh dependencies"
1. Close the project
1. Edit `encoreui.app.App` and make sure the version matches the next release version number
1. Package the app by running: `package`

### Build the toolbox package
1. Pull the latest encore-matlab repository changes and ensure everything is up-to-date by running: `git pull; git submodule foreach --recursive "(git checkout master; git pull)"; git status`
1. Open MATLAB
1. Change directory to the root encore-matlab directory
1. Generate the documentation from the wiki by running: `site`
1. Replace src/main/resources/docs with target/site
1. Add the lib and src directory and their child directories to the MATLAB path
1. Edit `encore.app.App` and make sure the version matches the next release version number (*this should generally be the same number used while building the UI app*)
1. Package the toolbox by running: `package`

The releasable toolbox (Encore.mltbx) is now under the target directory.
