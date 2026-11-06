# Depth Motion

Create an MP4 with alternating depth-based camera movements from a Premiere Pro sequence of still images. Each image keeps its original duration. The output is silent, so keep your original audio in Premiere. The effect estimates depth; it does not independently animate people.

> **Early test builds:** The Mac and Windows apps were tested on one computer each. Signing, broader compatibility and third-party license review are unfinished. Try a short preview before using a full project. Downloads are being prepared; see Releases for availability.

## Download and install

Choose the installer for your computer from this repository’s **Releases** page once a release is available. Each installer is about 400 MB and rendering requires additional disk space.

### Mac

- Supported test configuration: Apple silicon (M1 or newer), macOS 26 or newer. Intel Macs and older macOS versions have not been tested.
- Open the Mac .pkg installer and follow its instructions; then open Depth Motion from Applications.
- The test installer is unsigned and not notarized. macOS may warn or block it. The first render may download an AI model; image processing takes place locally.

### Windows

- Supported test configuration: 64-bit Windows 11. It was tested on one PC with Intel UHD Graphics; other systems and Windows on ARM are not yet verified.
- Open the Windows Setup .exe and follow its instructions; then open Depth Motion from the Start menu.
- The test installer is unsigned; Windows may warn or block it. The tested build includes the model and processes images locally.

Other operating systems have not been tested.

## Prepare the sequence in Premiere Pro

1. Arrange your still images in the order and durations you want, aligned to your audio.
2. Work from a copy with one uninterrupted, enabled video track of still images, starting at the sequence beginning. Remove gaps, transitions, nested sequences and video clips from that copy. Keep your audio tracks.
3. Use a progressive sequence with square pixels. Select it and choose **File → Export → Final Cut Pro XML**; save the XML.
4. Keep the source images in the locations referenced by the XML. When moving projects to another computer, relink media in Premiere and export a new XML there.

## Create your video

1. Open Depth Motion, click **Choose XML…**, and select the exported XML. Choose the sequence if needed.
2. Click **Create short preview** and save it with a new name. It uses the first three images at their actual durations.
3. Watch the preview. If you like it, click **Generate full video** and choose a new name. Leave the app open until the video is ready.
4. Import the MP4 into Premiere. Place it on a video track above the original still images, aligned to the sequence start. Keep your original audio.
5. Review framing and the cuts before final export. Five movement variations repeat across the images.

## Limitations

Existing effects, transformations, cropping and opacity are not reproduced. Complex depth edges may distort. Multiple populated tracks, gaps, transitions, nested clips and video clips are not supported. The app does not overwrite existing output videos and does not currently have a cancel button. Processing speed depends on the computer and images.

## Source and licensing

The Mac and Windows builds use different background-processing implementations and are not a single executable. Source and build instructions are being prepared. Third-party licensing and complete corresponding-source requirements have not yet been reviewed for distribution. DepthFlow and ShaderFlow use AGPL licenses; the FFmpeg builds contain GPL-enabled components; other dependencies have their own terms. Signing and wider testing remain outstanding.
