# StereoDroid

StereoDroid is a planned way to use an Android phone in a Cardboard-style viewer as a head-tracked VR headset for SteamVR on Linux. ALVR will send video from the PC to PhoneVR on the phone, while the phone sends head pose and commands back. The phone uses its sensors for head tracking and reprojects the last received frame while the next one is in transit.

The project is planned as a contribution to current ALVR upstream, including bringing PhoneVR up to date with it, and as Linux and Sparky Stereo OS packaging. The name was reserved on 2026-10-10. Nothing is built yet.

“Droid” is used descriptively. StereoDroid is not affiliated with any trademark holder.

## How it is planned to work

ALVR's server will run on the PC and use SteamVR/OpenVR to receive the rendered view and stream it to PhoneVR. PhoneVR is the open phone client, built on the Cardboard SDK. The phone sends its head pose and commands back over the same connection. The phone is the display the PC drives; it does not render the game.

When the phone connects, the desktop is planned to add a monitor in the viewer's mode at the phone's native resolution, like a 3D TV when plugged in. The phone will report its panel resolution, DPI, and refresh rate. The PC will render at that resolution, with half the panel width for each eye and no scaling.

The phone tracks head orientation, but accelerometers alone cannot provide reliable position. Position inferred by double-integrating acceleration drifts quickly. StereoDroid will use a neck model for small natural parallax. Camera tracking such as ARCore is not planned.

The user can recenter from a PC hotkey or gamepad combination. Phone settings will offer gyroscope and accelerometer orientation, which is steadier near metal and speakers, or magnetometer-assisted orientation to reduce slow yaw drift over long sessions. The phone app will include figure-eight sensor calibration.

While the phone is in the viewer, touch input is disabled and the gamepad connects to the PC. The phone's volume keys control display brightness while the app is in the foreground, without special permission. Brightness can also be controlled from KDE over the command channel. The same channel may report battery level and temperature and support do-not-disturb, keep-screen-on, lens, and eye-distance settings. Battery and temperature reporting is a proposal for review. Heat will be a user setting: “Automatic (ease off when hot)” or “Full power until it drops.”

## Sound

The sound setting will read “Sound: on the PC (recommended) / streamed to the phone.” Sound stays on the PC by default and plays through the user's headphones or speakers. The phone receives video and sends head pose and commands, without audio decode or Bluetooth transmission on the phone. This reduces phone work, streaming, and battery use. A large-battery, high-DPI phone is a good fit. Bluetooth can add about 100–200 ms of sound delay unless a low-latency codec such as aptX Low Latency or LC3/LE Audio is used, or a dongle headset is used. Both paths need measurement.

The PC keeps the game's multichannel 5.1 or 7.1 mix whole to the audio output. The planned sound modes are Headphones and Room speakers. Headphones use binaural rendering for ordinary headphones and turn the sound field with the head pose. For a headset that accepts multichannel audio, the PC can send the multichannel mix directly.

Room speakers will send the game's multichannel mix to physical speakers, such as 5.1 analog outputs or HDMI LPCM or passthrough to an AV receiver. This avoids Bluetooth delay. The mode will counter-rotate the game's head-relative sound field by head yaw so that sounds stay anchored to the room. The proposed path is to encode the 5.1 or 7.1 mix to ambisonics, rotate it by negative head yaw, and decode it to the configured speaker layout. The PipeWire spatializer controls and packaged open rotators need investigation. Their latency and the head-tracked binaural path need measurement before either is promised to work.

## Links and video

The planned links are home Wi-Fi by default, the PC's own hotspot with the phone connected directly, or USB cable. KDE Connect will be optional. The phone is also planned to be found over the local network through UPnP. The hotspot avoids the home router and needs no extra dongle. USB avoids Wi-Fi and charges the phone. The link options need measurement.

The video encoder will aim for a steady bitrate and adapt slowly. Keyframe work will be spread to limit visible artifacts. StereoDroid will render and encode the full panel evenly at native resolution. It will not use foveated streaming. ALVR's foveated encoding will be off. Artifacts and latency need measurement at each setting.

## Movie mode

The phone app is also planned as a DLNA renderer. Universal Media Server or another DLNA server can send a movie to the phone for decoding there. A stereo movie shows split per eye with the lens correction, and a 2D movie as one flat screen to both eyes. Brightness and volume can be set from the PC or from any DLNA controller.

## Related project

[Flat Headset](../flat-headset/README.md) is the no-tracking sibling. It uses the phone as a 3D desktop screen without head tracking.

## Sparky Stereo OS

StereoDroid is planned as part of [Sparky Stereo OS](https://github.com/Sparky-OS/sparky-stereo-os). Its design follows the [house formats](https://github.com/Sparky-OS/sparky-stereo-os/blob/main/docs/house-formats.md) used by that project.

Sparky Stereo OS, Daniel Ramos's edition of SparkyLinux (by Paweł "pavroo" Pijanowski).

Licence: GPL-2.0-only OR GPL-3.0-only OR LicenseRef-KDE-Accepted-GPL, the licence of KDE Connect for Android, so the code can go upstream to KDE unchanged (texts in `LICENSES/`).
