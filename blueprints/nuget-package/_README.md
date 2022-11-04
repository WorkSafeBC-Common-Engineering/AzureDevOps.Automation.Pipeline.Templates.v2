Nuget Package pipeline templates

To use these templates:
1. Copy the "azure-pipeline-nuge-package-start.yml" file (the Start file) into your project. This should be in the root of the project repo.
2. Edit the Start file as follows:
   - in the trigger section, replace the TODO for the paths/include to indicate the path to your source files.
   - Locate the "extends" section.
   - There are two "control" templates - one is for .Net Framework projects (azure-pipeline-nuget-dotNetFW-control.yml), the other is for .Net Core and .Net Standard projects (azure-pipeline-nuget-dotNetCore-control.yml). You will need to specify which template you wish to extend to.
   - If you select the .Net Framework control template, you will need to set the following parameters:
     - portfolioName
     - productName
     - projectName
     - platform
     - nuspecPath
     - suppressCD
     - modeElite
     - verbose
   - If you select the .Net Core control template, you will need the following parameters:
     - netCoreVersion
     - portfolioName
     - productName
     - projectName
     - platform
     - nuspecPath
     - suppressCD
     - modeElite
     - verbose
3. These parameters need to be set as follows:
   - netCoreVersion: Version of .Net Core to be used in compiling the application, only used by .Net Core projects. This should be in the format of Major.minor.release. Example, you could specify "6.*" to get the current major version of Net 6, or "6.0.*" to get the current release of .Net Core 6.0.
   - portfolioName:  Portfolio this package will be under. Ex: IT-App-Delivery
   - productName:    Product name of this package.
   - projectName:    Name of the project where the package will be created from.  For example, if you building the project in the "Sample.csproj" project, you would specify "Sample".
   - platform:       Build Platform. This can be x86, x64, or AnyCPU. If not specified, will default to AnyCPU. Other values can be specified based on the project settings.
   - nuspecPath:     Full path to the .nuspec file that defines the package parameters.  
   - suppressCD:     If true, then the package will only be built and saved as an artifact. By default this will be false. NOTE: at this time CD is not yet completed, so this value is being forced to true at this time. Once the CD templates have been completed, this flag will be accessible again.
   - modeElite:      Internal use - leave as false, or do not include this parameter.
   - verbose:        Setting this to true will result in more verbose logging of the CI/CD process. Can be used to debug issues. By default this value will be set to false if not specified.
