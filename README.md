### Eset Log Collector Test Project

I tried to automate a basic user's scenarios for the **ESET Log Collector Application v2.0.6.0. (CSY language location). 
An implementation of the tests in the *LogCollectorUiTests.cs* class is based on the window object design pattern (the 'window' object as an equivalent to the 'page' object in the context of desktop applications) to represent the UI elements of the desktop application in more concise and readable way. In the *LogCollectorAppWindow* directory you can find all item's locators so that you can update them in a single location. Also, I defined all common actions in one place to avoid of the code redundancy.
Moreover, I leveraged partial classes to separate the different components of the window object: actions, assertions and elements. 

Test automation tools:
- Microsoft Visual Studio Community 2019 v16.8.0
- NUnit v3.12.0
- NUnit3TestAdapter v3.17.0
- WindowsApplicationDriver v1.2.1
- Appium.WebDriver v4.2.1
- MSTest.TestFramework v2.1.2
- Microsoft.NET.Test.Sdk Version=16.8.0
- inspect.exe (can be found under the Windows SDK folder which is typically `C:\Program Files (x86)\Windows Kits\10\bin\x86`)

### Windows Application Driver

Windows Application Driver (WinAppDriver) is a service to support Selenium-like UI Test Automation on Windows Applications. This service supports testing Universal Windows Platform (UWP), Windows Forms (WinForms), Windows Presentation Foundation (WPF), and Classic Windows (Win32) apps on Windows 10 PCs. 

Install & Run WinAppDriver
1. Download Windows Application Driver installer from https://github.com/Microsoft/WinAppDriver/releases
2. Run the installer on a Windows 10 machine where your application under test is installed and will be tested
3. Enable [Developer Mode](https://docs.microsoft.com/en-us/windows/uwp/get-started/enable-your-device-for-development) in Windows settings
4. Run WinAppDriver.exe as *administrator* from the installation directory (E.g. C:\Program Files (x86)\Windows Application Driver)

Windows Application Driver will then be running on the test machine listening to requests on the default IP address and port (`127.0.0.1:4723`). You can then run any of our [Tests](/Tests/) or [Samples](/Samples). `WinAppDriver.exe` can be configured to listen to a different IP address and port as follows:

WinAppDriver.exe 4727
WinAppDriver.exe 10.0.0.10 4725
WinAppDriver.exe 10.0.0.10 4723/wd/hub

Note: You must run WinAppDriver.exe as *administrator* to listen to a different IP address and port.

### Creating a Test Project

1. Open Microsoft Visual Studio 2019
2. Create the test project and solution. I.e. Select New Project > Templates > Visual C# > Test > Unit Test Project
3. Once created, select Project > Manage NuGet Packages... > Browse and search for Appium.WebDriver
4. Install the Appium.WebDriver NuGet packages for the test project
5. Start writing your test
