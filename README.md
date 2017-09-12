# VSTS Extension

SoapUI extension for VSTS

This extension can be used to run SoapUI script or to make SoapUI available for other tasks (as an environment variable).

[SoapUI](https://www.soapui.org/) version used is version 5.3

# Usage

- Go to VSTS Marketplace and install the extension
- In your build definition add the task "SoapUI"
  - Either select your project (and [arguments](https://www.soapui.org/test-automation/running-functional-tests.html))
- or "SoapUI-Include"
  - This will create an environment variable called SOAPUI_EXE that you can use in the following tasks.

To test that the task works properly, you can download [project.xml](../blob/master/project.xml) and use it as a test script. (TODO)

In both tasks, SoapUI will be downloaded the first time the task is called from http://cdn01.downloads.smartbear.com/soapui/5.3.0/SoapUI-5.3.0-windows-bin.zip
The next call will simply use the downloaded file without re doanloading it.

For Hosted Agents, SoapUI will be downloaded each time the task is called.

# Availability

This extension is publicly available on VSTS Marketplace: https://marketplace.visualstudio.com/items?itemName=ThomasP.soapui-tasks

It is build in VSTS using VSTS Developer Tools Build Task (https://marketplace.visualstudio.com/items?itemName=ms-devlabs.vsts-developer-tools-build-tasks).
Here is the status: ![Build status](https://tomap.visualstudio.com/_apis/public/build/definitions/6e176905-7621-4cdb-97ba-78eb0fd1e1ed/5/badge)

The build number is automaticaly incremented on each commit by the VSTS Build task by a pattern like "0.0.$(Build.BuildId)". See https://www.visualstudio.com/en-us/docs/build/define/variables#predefined-variables for reference.

# License

This extension is published under MIT license. See [license file](../blob/master/LICENSE).