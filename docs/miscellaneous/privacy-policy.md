# Privacy Policy

**Last Updated**: October 9, 2025

---

Blueprint Assist does not automatically collect any personal data.

To help find and fix bugs, Blueprint Assist includes a crash reporting feature.

Sending a crash report is completely optional. When a crash occurs, on the next editor launch you will be asked for your
consent to send the report.

## What data is collected

If you choose to send a report, the following data will be collected:

1. **Crash Context**: This file contains the crash call stack, details about your OS and Unreal
   installation. It is a filtered version of the `CrashContext.runtime-xml` normally sent to Epic Games. We take steps
   to anonymize this data, including attempting to filter out sensitive information like local file paths from the call
   stack. You can find an example crash context at the [bottom of this page](#example-crash-context).
2. **(_Optional_) Crash related nodes**: Nodes that may have triggered the crash when formatting. This will not send
   your entire blueprint, only the linked nodes in text format.
3. **(_Optional_) Blueprint Assist settings**: Your current Blueprint Assist settings.

## Data Retention and Storage

This data will be stored on BugSplat servers for a maximum of 30 days before being automatically deleted. Some crash
reports may be saved locally for a longer period until the associated bug is resolved.

## Third-Party Services

We use [BugSplat](https://www.bugsplat.com) to manage and analyze these crash reports. You can
find more details in their
[security and compliance documentation](https://docs.bugsplat.com/introduction/production/security-privacy-and-compliance).

## Your Rights

You have the right to request access to or deletion of any crash report data you have submitted.

Since the crash reports are anonymous, you must provide the associated **Report ID**.
Without it, we have no way to identify your specific report and fulfill the request.

The **Report ID** can be found at: `{Project}/Saved/Crashes/BACrashData/{ReportID}`.  
Example ID: `UECC-Windows-B54EF88243B5194B7B3140BECB7B6610_0000`.

## Changes to This Policy

We may update this privacy policy from time to time. The **Last Updated** date at the top of this page will indicate the
latest revision.

## Contact

If you have any questions, please contact us at `func.pwong@gmail.com`

---

## How it works

When you launch the editor, the plugin searches your recent crashes in `{Project}/Saved/Crashes`, if any of
the callstacks relate to Blueprint Assist you will be prompted to send a crash report.

If the editor crashes while formatting, related nodes will be saved to a file.
Sending this data is optional and you will have to tick a checkbox in the crash reporter before sending.

Blueprint Assist crash report data is saved to `{Project}/Saved/Crashes/BACrashData/`.

!!! note "Crash reporting settings in `Blueprint Assist Advanced`"
    * **DumpFormattingCrashNodes**: Save formatting related nodes to file on crash
    * **CrashReportingMethod**: `Ask` (ask on launch), `Never` (never prompt to send crash reports)

## Example crash context

```xml
<?xml version="1.0" encoding="UTF-8"?>
<FGenericCrashContext>
    <RuntimeProperties>
        <CrashGUID>UECC-Windows-B54EF88243B5194B7B3140BECB7B6610_0000</CrashGUID>
        <IsEnsure>false</IsEnsure>
        <IsStall>false</IsStall>
        <IsAssert>false</IsAssert>
        <CrashType>Crash</CrashType>
        <ErrorMessage>Unhandled Exception: EXCEPTION_ACCESS_VIOLATION reading address 0x0000000000000050</ErrorMessage>
        <CrashReporterMessage/>
        <CrashReporterMessage>Attended</CrashReporterMessage>
        <IsWithDebugInfo>true</IsWithDebugInfo>
        <IsSourceDistribution>false</IsSourceDistribution>
        <BuildConfiguration>Development</BuildConfiguration>
        <PlatformName>WindowsEditor</PlatformName>
        <PlatformFullName>Win64 [Windows 11 (24H2) [10.0.26100.6584] 64b]</PlatformFullName>
        <PlatformNameIni>Windows</PlatformNameIni>
        <EngineMode>Editor</EngineMode>
        <EngineVersion>5.6.1-44394996+++UE5+Release-5.6</EngineVersion>
        <EngineCompatibleVersion>5.6.1-44394996+++UE5+Release-5.6</EngineCompatibleVersion>
        <BuildVersion>++UE5+Release-5.6-CL-44394996</BuildVersion>
        <IsUERelease>true</IsUERelease>
        <IsRequestingExit>false</IsRequestingExit>
        <SourceContext/>
        <UserDescription/>
        <UserActivityHint>Layout=&quot;Document&quot; Label=&quot;EventGraph&quot; Content=SGraphEditor
        </UserActivityHint>
        <Misc.NumberOfCores>6</Misc.NumberOfCores>
        <Misc.NumberOfCoresIncludingHyperthreads>12</Misc.NumberOfCoresIncludingHyperthreads>
        <Misc.Is64bitOperatingSystem>1</Misc.Is64bitOperatingSystem>
        <Misc.CPUVendor>AuthenticAMD</Misc.CPUVendor>
        <Misc.CPUBrand>AMD Ryzen 5 7500F 6-Core Processor</Misc.CPUBrand>
        <Misc.OSVersionMajor>Windows 11 (24H2) [10.0.26100.6584]</Misc.OSVersionMajor>
        <Misc.OSVersionMinor/>
        <CallStack>UnrealEditor_BlueprintAssist!FEdGraphFormatter::FormatNode()
            [BlueprintAssist/Private/BlueprintAssistFormatters/EdGraphFormatter.cpp:82]
            UnrealEditor_BlueprintAssist!FBAGraphHandler::FormatNodes()
            [BlueprintAssist/Private/BlueprintAssistGraphHandler.cpp:3538]
            UnrealEditor_BlueprintAssist!FBAGraphHandler::UpdateNodesRequiringFormatting()
            [BlueprintAssist/Private/BlueprintAssistGraphHandler.cpp:2724]
            UnrealEditor_BlueprintAssist!FBAGraphHandler::Tick()
            [BlueprintAssist/Private/BlueprintAssistGraphHandler.cpp:494]
            UnrealEditor_BlueprintAssist!FBATabHandler::Tick()
            [BlueprintAssist/Private/BlueprintAssistTabHandler.cpp:53]
            UnrealEditor_BlueprintAssist!FBAInputProcessor::Tick()
            [BlueprintAssist/Private/BlueprintAssistInputProcessor.cpp:101]
            UnrealEditor_Slate!FSlateApplication::FinishedInputThisFrame()
            [Runtime/Slate/Private/Framework/Application/SlateApplication.cpp:1459]
            UnrealEditor!FEngineLoop::Tick() [Runtime/Launch/Private/LaunchEngineLoop.cpp:5614]
            UnrealEditor!GuardedMain() [Runtime/Launch/Private/Launch.cpp:187]
            UnrealEditor!GuardedMainWrapper() [Runtime/Launch/Private/Windows/LaunchWindows.cpp:128]
            UnrealEditor!LaunchWindowsStartup() [Runtime/Launch/Private/Windows/LaunchWindows.cpp:282]
            UnrealEditor!WinMain() [Runtime/Launch/Private/Windows/LaunchWindows.cpp:339]
            UnrealEditor!__scrt_common_main_seh()
            [D:/a/_work/1/s/src/vctools/crt/vcstartup/src/startup/exe_common.inl:288]
            kernel32
            ntdll
        </CallStack>
    </RuntimeProperties>
    <EngineData>
        <DeviceProfile.Name>WindowsEditor</DeviceProfile.Name>
        <Platform.AppHasFocus>true</Platform.AppHasFocus>
        <BAGraphHint>EdGraph</BAGraphHint>
        <BAAssetHint>Blueprint</BAAssetHint>
    </EngineData>
</FGenericCrashContext>
```