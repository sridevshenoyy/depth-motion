# Installation warnings for Depth Motion

The current test installers are **unsigned**. The Mac app is also **not notarized by Apple**. macOS and Windows cannot verify the publisher, and the apps have not been independently certified as safe. The builds have only been tested on one Mac and one Windows PC. Download only from the [official Depth Motion test release](https://github.com/sridevshenoyy/depth-motion/releases/tag/v0.2.0-test), and proceed only if you trust the source and the file has not been tampered with. You do not need to turn off all security settings.

## Mac

The test build is for Apple silicon (M1 or newer), macOS 26 or newer; other Macs have not been tested.

1. Download the Mac `.pkg` from the test release and try to open it. If macOS blocks it because the developer cannot be verified, close the warning.
2. Open **Apple menu → System Settings → Privacy & Security**. Scroll to the Security section and select **Open Anyway** for the installer. The button is usually available for about an hour after the attempt.
3. Confirm **Open** and enter your Mac administrator password if requested. Follow the installer instructions, then open Depth Motion from Applications.
4. If the installed app gets a similar unidentified developer warning, repeat the same process for the app itself.

This creates an exception for the app; it does not switch off all Mac security. If macOS reports that the file contains malware, will damage your computer, or is damaged, stop and contact the project instead of proceeding. Managed Macs may need an administrator. See [Apple's instructions](https://support.apple.com/en-us/102445).

## Windows

The test build was tested on a 64-bit Windows 11 PC; other configurations have not been verified.

1. Download `Depth-Motion-0.2.0-Windows-Setup.exe` from the test release and open it.
2. If Microsoft Defender SmartScreen says **Windows protected your PC** because the app is unrecognized, review the file details. If you trust the downloaded file, select **More info → Run anyway**, if those options are available.
3. If Windows asks for administrator permission, review the request and approve only if you trust the installer. Follow the setup instructions and open Depth Motion from the Start menu.

Keep antivirus and other security protections enabled. A malware detection, a browser download block, an organization policy, and a SmartScreen reputation warning are different things; these steps may not apply to all of them. If Windows reports malware or the file looks unexpected, stop and contact the project. If **Smart App Control** blocks the app, Microsoft says it does not offer an individual app exception. Do not disable it just to install this test build; contact the project or your administrator instead. See [Microsoft's SmartScreen guidance](https://learn.microsoft.com/en-us/windows/apps/package-and-deploy/publish-first-app) and [Smart App Control FAQ](https://support.microsoft.com/en-us/windows/security/threat-malware-protection/smart-app-control-frequently-asked-questions).
