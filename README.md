# Depth Motion

Create a silent MP4 with alternating depth-based camera movement from a Premiere Pro sequence of still images. Each image keeps its original duration. Keep your original audio in Premiere; this effect estimates depth and does not independently animate people.

> **Early test builds:** The Mac and Windows apps were each tested on one computer. Signing, broader compatibility and third-party license review are unfinished. Try a short preview before using a full project.

## Download and install

Go to the [test release](https://github.com/sridevshenoyy/depth-motion/releases/tag/v0.2.0-test) and download the installer for your computer. Each installer is roughly 400 MB; rendering needs additional free disk space.


[Installation warning instructions for Mac and Windows](INSTALLATION-WARNINGS.md).
### Mac

- Tested configuration: Apple silicon (M1 or newer), macOS 26 or newer. Intel Macs and older macOS versions have not been tested.
- Open the Mac .pkg installer, follow the instructions, then open Depth Motion from Applications.
- This build is unsigned and not notarized, so macOS may warn or block it. The first render may download an AI model. Image processing takes place on your Mac.

### Windows

- Tested configuration: 64-bit Windows 11 on one PC with Intel UHD Graphics. Other computers, graphics hardware, and Windows on ARM have not been verified.
- Open the Windows Setup .exe, follow the instructions, then open Depth Motion from the Start menu.
- This build is unsigned, so Windows may warn or block it. The tested installer includes the model and video tools; rendering is local.

Other operating systems have not been tested.

## Prepare your sequence in Premiere Pro

1. Arrange your still images in order and set their durations to match your audio.
2. Work from a copy with one uninterrupted, enabled video track of still images starting at the sequence beginning. Remove video gaps, overlaps, transitions, nested sequences and video clips from that copy. Keep your audio tracks.
3. Use a progressive sequence with square pixels. Select the sequence and choose **File → Export → Final Cut Pro XML**, then save the XML.
4. Keep the source images in the locations referenced by the XML. If you move the project, relink media in Premiere and export a fresh XML on that computer.

## Create your video

1. Open Depth Motion, click **Choose XML…**, and select the XML. Choose the sequence if needed.
2. Click **Create short preview** and choose a new filename. The preview uses the first three images at their actual durations.
3. Watch the preview. If you like it, click **Generate full video** and choose a new filename. Leave the app open until it says the video is ready.
4. Import the MP4 into Premiere and place it on a video track above your original images, aligned to the sequence start. Keep the original audio tracks.
5. Review framing and image cuts before the final export. Five movement variations repeat across the images.

## Limitations

Existing effects, transforms, cropping and opacity changes are not reproduced. Estimated depth may distort fine details. Multiple populated video tracks, gaps, transitions, nested clips and video clips are not supported. The app does not overwrite an existing output and currently has no cancel button. Speed depends on the computer and images.

## Source and licensing

The Mac and Windows builds use different background processors and are not a single executable. The [prototype source archive](Depth-Motion-source-preview.zip) contains platform source and build notes. Third-party licensing and complete corresponding-source requirements have not yet been reviewed for distribution. DepthFlow and ShaderFlow use AGPL licenses; the FFmpeg builds contain GPL-enabled components; other dependencies have their own terms. See [third-party provenance](THIRD-PARTY-PROVENANCE.md). Signing and broader testing remain outstanding.
