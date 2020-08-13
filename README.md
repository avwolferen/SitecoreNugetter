# SitecoreNugetter

The easiest way on getting all Sitecore 10.0.0 (and other versions) NuGet supported NuGet packages downloaded into one single folder. Hassle free!
This repository goes with the blogpost https://www.alexvanwolferen.nl/download-all-485-nuget-packages-for-sitecore-10-0-0-with-this-one-line-command-in-under-3-minutes/

## Step 1 Execute one-line command from Package Manager Console
Go to the Package Manager Console and execute the following command (this could take a while because it will collect the entire dependency graph of Sitecore 10.0.0).

$version="10.0.0";$targetDirectory=".\sitecore1000";Install-Package -Id Sitecore -Version $version -Source https://sitecore.myget.org/F/sc-packages/api/v3/index.json -DependencyVersion Lowest;if (-not (Test-Path $targetDirectory)){New-Item -Path $targetDirectory -Type Directory};Copy-Item -Path ".\packages\**\*.nupkg" -Destination $targetDirectory -Recurse -Force

## Finished!
Have fun with all those packages!