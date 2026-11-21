# StereoDroidVR

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23309026.svg)](https://doi.org/10.5281/zenodo.23309026)

StereoDroidVR is the Android phone headset project for PC VR with head tracking. The PC renders the world; the phone, in a Cardboard-style viewer, decodes and presents the two eyes and reports head orientation.

The complete tracked RDP headset is not yet qualified. Earlier work proves individual parts: Android orientation and camera delivery through RDP, and OpenVR programs through xrizer into the PC's OpenXR runtime. The earlier PhoneVR/ALVR experiments prove their own transport and viewer, not this RDP integration. This repository contains documentation. The Android implementation is the StereoDroidVR function in [Flat Headset’s shared application source](https://github.com/Sparky-OS/flat-headset), with its own launcher entry and the same KDE Connect identity and pairing as the flat receiver.

## One paired session

KDE Connect pairing is required before connecting. Picture and head pose use the same authenticated RDP session: video travels to the phone, and orientation returns on the edition's dynamic virtual channel. Camera frames use RDP camera redirection for hand tracking on the PC. A separate ALVR or WiVRn transport is not part of this design.

OpenXR is the PC rendering boundary. OpenVR applications reach it through xrizer. Running an OpenVR application this way does not establish that the SteamVR runtime itself works with the phone; that qualification remains separate.

Connection adds a virtual monitor already in the headset mode. Each source hands Stereo KWin full side by side, left eye first, at the chosen resolution per eye. KWin owns the output conversion. The phone link keeps half side by side for latency; it is an encoding choice of the link, not another game setting.

Depth limits belong to the person's Display Settings and are applied once. The headset uses the edition's existing headset separation policy. No application rescales those limits or adds another depth control.

## Tracking, lenses and sound

The RDP orientation prototype uses Android's fused game rotation vector, with an explicit compass-assisted choice. The PC receives the original capture timestamp and converts the orientation into its head coordinate system. Rotation alone does not establish measured position. Recentering, sensor restart, stale input, permission revocation and reconnect must preserve explicit tracking state; a lost source must not silently become an untracked session.

The viewer's lens calibration and presentation must be qualified with tracking enabled, including retained-frame reprojection and both landscape mountings. Existing PhoneVR/Cardboard results are evidence for that viewer, not proof that the RDP viewer already implements the same behavior.

Room-speaker audio must remain anchored to the room as the head turns. Earlier isolated rotation tests do not prove a complete continuously tracked 5.1 or 7.1 path. That integration remains open.

## Related programs

[Flat Headset](https://github.com/Sparky-OS/flat-headset) is the static stereo desktop and movie receiver, with no head tracking. StereoDroidVR is the tracked function in that same Android application, reached through its own icon. iStereoVR is the corresponding future tracked iPhone program. Choosing the other Android function ends the old session and starts a new one with the existing pairing. Seamless automatic switching between functions is separate work.

ALVR and WiVRn remain use-only references for this project. Their contribution policies were rechecked on 2026-11-20: [ALVR](https://github.com/alvr-org/ALVR/blob/main/CONTRIBUTING.md) prohibits AI contributions, and [WiVRn](https://github.com/WiVRn/WiVRn/blob/master/AGENTS.md) prohibits agent pull requests and issue interaction. No contribution to either is planned here.

## Sparky Stereo OS

StereoDroidVR is part of [Sparky Stereo OS](https://github.com/Sparky-OS/sparky-stereo-os). Its design follows the edition's [house formats](https://github.com/Sparky-OS/sparky-stereo-os/blob/main/docs/house-formats.md). The repository URL keeps its existing spelling. “Droid” is used descriptively; StereoDroidVR is not affiliated with any trademark holder.

Sparky Stereo OS, Daniel Ramos's edition of SparkyLinux (by Paweł "pavroo" Pijanowski).

Licence of this repository: GPL-2.0-only OR GPL-3.0-only OR LicenseRef-KDE-Accepted-GPL (texts in `LICENSES/`). Dependencies retain their own licences; see [ATTRIBUTIONS.md](ATTRIBUTIONS.md).
