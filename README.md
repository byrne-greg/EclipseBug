# EclipseBug
Demonstration of an eclipse bug

## Problem

Importing existing projects into eclipse do not respect the Project name as defined in the `.project` file depending on when the workspace is located in the code's top level directory.

## Reproduce

1. Open Eclipse
2. Switch the workspace to the `/EclipseBug/` directory
3. Select from Eclipse top menu `File` -> `Import` -> `General` -> `Existing projects into workspace`
4. Use the currenct directory (`/EclipseBug/`) as the root directory and ensure Search for nested projects is selected
5. The projects that should be displayed are `CoreInf` and `NotCoreInf` (as expected, using the `.project` name)
6. Switch the workspace to the `/EclipseBug/myWorkspace/` directory
7. Select from Eclipse top menu `File` -> `Import` -> `General` -> `Existing projects into workspace`
8. Use the currenct directory (`/EclipseBug/myWorkspace/`) as the root directory and ensure Search for nested projects is selected
9. The projects that should be displayed are `CoreInf` and `coreinf` (not expected, using the directory name)

## Result

### Expected 
When the workspace is set to the top level directory of the projects, Eclipse should import using the project name rather than the subdirectory name of the project.
