# Looking for someone to maintain this project

Hi, I'm looking for someone to take over this project as I no longer have time to dedicate to it.

If you would like to do so, please contact me via an issue, make a fork and do your first change.
I can help you set up the CI and indicate on this README who is maintaining the project (name & url).

-------------------------------------------------------------

# VSTS Extension

SoapUI extension for VSTS

This extension can be used to run SoapUI script or to make SoapUI available for other tasks (as an environment variable).

[SoapUI](https://www.soapui.org/) version used is version 5.4

# Usage

- Go to VSTS Marketplace and install the extension
- In your build definition add the task "SoapUI"
  - Either select your project (and [arguments](https://www.soapui.org/test-automation/running-functional-tests.html))
    - If you add the argument -j (default value), this task will produce junit reports, which you can then send to VSTS/TFS using task "[Publish Test Results](https://docs.microsoft.com/en-us/vsts/build-release/tasks/test/publish-test-results)"
- or "SoapUI-Include"
  - This will create an environment variable called SOAPUI_EXE that you can use in the following tasks.

To test that the task works properly, you can download [project.xml](../blob/master/project.xml) and use it as a test script. (TODO)

In both tasks, SoapUI will be downloaded the first time the task is called from https://s3.amazonaws.com/downloads.eviware/soapuios/5.4.0/SoapUI-5.4.0-windows-bin.zip
The next call will simply use the downloaded file without re downloading it.

For Hosted Agents, SoapUI will be downloaded each time the task is called.

# Availability

This extension is publicly available on VSTS Marketplace: https://marketplace.visualstudio.com/items?itemName=ThomasP.soapui-tasks

It is build in VSTS using VSTS Developer Tools Build Task (https://marketplace.visualstudio.com/items?itemName=ms-devlabs.vsts-developer-tools-build-tasks).
Here is the status: ![Build status](https://tomap.visualstudio.com/_apis/public/build/definitions/6e176905-7621-4cdb-97ba-78eb0fd1e1ed/5/badge)

The build number is automatically incremented on each commit by the VSTS Build task by a pattern like "0.0.$(Build.BuildId)". See https://www.visualstudio.com/en-us/docs/build/define/variables#predefined-variables for reference.

# License

This extension is published under MIT license. See [license file](../blob/master/LICENSE).
