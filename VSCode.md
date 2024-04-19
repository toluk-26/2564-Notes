https://software-dl.ti.com/ccs/esd/documents/ccs_projects-command-line.html

`eclipsec -noSplash -data "<workspace_dir>" -application com.ti.ccstudio.apps.projectBuild (-ccs.projects <name1>[ <name2>]* | -ccs.workspace) [<options>]`

Clean the active build-configuration of project 'newProject' without building it:  
`eclipsec -noSplash -data "C:\myWorkspace" -application com.ti.ccstudio.apps.projectBuild -ccs.projects newProject -ccs.clean`

Rebuild the 'Debug' build-configuration of project 'newProject':  
`eclipsec -noSplash -data "C:\myWorkspace" -application com.ti.ccstudio.apps.projectBuild -ccs.projects newProject -ccs.configuration Debug`


