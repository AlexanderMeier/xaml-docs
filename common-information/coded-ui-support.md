---
title: Coded UI support
page_title: Coded UI support
description: The article describes the CodedUI support of the Telerik suite.
slug: coded-ui-support
tags: coded,ui,support
published: True
position: 8
site_name: WPF
---

# Coded UI support

The purpose of this section is to show you how to create a simple CodedUI test. 

For more information about Creating, Editing and Maintaining a Coded UI Test check out the official page in MSDN [here](http://msdn.microsoft.com/en-us/library/ff977233.aspx).        

For Visual Studio versions 2017 and later, please make sure that you have [Installed the coded UI test component](https://docs.microsoft.com/en-us/visualstudio/test/use-ui-automation-to-test-your-code?view=vs-2017#install-the-coded-ui-test-component) as it is not installed automatically.

>important The supported Visual Studio editions for coded UI tests are __Microsoft Visual Studio Ultimate, Premium and Enterprise__. You can also check [Supported Configurations and Platforms for Coded UI Tests and Action Recordings](https://msdn.microsoft.com/en-us/library/dd380742(v=vs.110).aspx).

> Coded UI is supported up to Visual Studio 2019. Visual Studio 2022 droppped the Coded UI feature.

In order to create a CodedUI test, you need to perform the following steps:

* Add the __Telerik.VisualStudio.TestTools.UITest.Extension.ExtensionsCore__ assembly into the following directory (for 64-bit operating system):          

	* For Microsoft Visual Studio 2010: "%CommonProgramFiles(x86)%\Microsoft Shared\VSTT\\__10.0__\UITestExtensionPackages".              

	* For Microsoft Visual Studio 2012: "%CommonProgramFiles(x86)%\Microsoft Shared\VSTT\\__11.0__\UITestExtensionPackages".      

	* For Microsoft Visual Studio 2013: "%CommonProgramFiles(x86)%\Microsoft Shared\VSTT\\__12.0__\UITestExtensionPackages".
	
	* For Microsoft Visual Studio 2015: "%CommonProgramFiles(x86)%\Microsoft Shared\VSTT\\__14.0__\UITestExtensionPackages" - added with version __2015 Q2 SP__.
	
	* For Microsoft Visual Studio 2017: "%CommonProgramFiles(x86)%\Microsoft Shared\VSTT\\__15.0__\UITestExtensionPackages" - added with version __2017 R1__.
	
	* For Microsoft Visual Studio 2019: "%CommonProgramFiles(x86)%\Microsoft Shared\VSTT\\__16.0__\UITestExtensionPackages" - added with version __2019 R1__.

	>For 32-bit operating systems, the path should be "%CommonProgramFiles%\Microsoft Shared\VSTT\\__[Version]__\UITestExtensionPackages".

	>tip You can find the  __Telerik.VisualStudio.TestTools.UITest.Extension.ExtensionsCore.dll__ file in the UI for WPF installation folder - usually C:\Program Files\Progress\Telerik UI for WPF [version]\Binaries\WPF40\\__TestTools__\VS[version]\

* The __Telerik.VisualStudio.TestTools.UITest.Extension.ExtensionsCore__ assembly must be installed into the global assembly cache (GAC). You can achieve this following the next steps:
	1. Open Visual Studio Command Prompt.
	2. Navigate to path "%CommonProgramFiles(x86)%\microsoft shared\VSTT\\__[Version]__\UITestExtensionPackages".
	3. Execute "gacutil /i Telerik.VisualStudio.TestTools.UITest.Extension.ExtensionsCore.dll".
 
	You can also find more information on the [Global Assembly Cache Tool (Gacutil.exe)](http://msdn.microsoft.com/en-us/library/ex0ss12c(v=vs.80).aspx).          

* Create WPF Project with the control you want to test.

* Add a new TestProject.

* Add new item to TestProject - Coded UI Test. The __Generate Code for Coded UI Test__ dialog box appears.          

* Select the __Record actions, edit UI map or add assertions__ option and choose __OK__. For more information about the options in the dialog box, you could check the [Use UI Automation To Test Your Code](http://msdn.microsoft.com/en-us/library/dd286726.aspx) MSDN article.

* Record a sequence of actions.

* Verify the values in UI properties.

* Run the test.

Below you can find information about the supported level of CodedUI tests throughout our controls.     

There is [Level 2 and Level 3 Coded UI test support](https://devblogs.microsoft.com/devops/coded-ui-test-extension-for-3rd-party-controls-the-basics-explained/) across our controls. For exceptions see bellow.
        
## Q2 2015

The controls that currently do __not__ support Level 2 and Level 3 Coded UI tests are listed bellow:
        
Control	|	Level 1	|	Level 2	|	Level 3
---	|	---	|	---	|	---
RadChart	|	No	|	No*	|	No*
RadGanttView	|	Yes	|	No	|	No
RadPivotGrid	|	Yes	|	No	|	No
RadScheduleView	|	Yes	|	No	|	No 

Use RadChartView instead of RadChart. For more information, please go through the [RadChart vs. RadChartView]({%slug radchartview-radchartview-vs-radchart%}) article. 

## Q2 2014

With __Q2 2014__ release of Telerik UI for WPF we have included [Level 4 Coded UI test support](https://devblogs.microsoft.com/devops/coded-ui-test-extension-for-3rd-party-controls-the-basics-explained/) for two of our controls. The following table gives more details on the controls as well as the supported actions:

Control	|	Action	|	Occurs	|	Action Property
---	|	---	|	---	|	---
RadComboBox	|	SetValueAction	|	On selection	|	SelectedItem
RadDateTimePicker	|	SetValueAction	|	On SelectedValue changed	|	DateTimeText

## Q3 2012

With __Q3 2012__ official release we have included [Level 1 Coded UI test support](https://devblogs.microsoft.com/devops/coded-ui-test-extension-for-3rd-party-controls-the-basics-explained/) across all controls, except __RadChart__ control.  

## See Also 
* [UI Automation Support]({%slug common-ui-automation%})
