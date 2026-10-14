# Attributions

StereoDroid is planned to use or build on the projects below. Contributor names are copied from project records and full-history `git shortlog -sn` output. The shortlog counts commits by recorded author. It does not show the amount or exact kind of work by each person.

## ALVR

[ALVR](https://github.com/alvr-org/ALVR) provides the planned PC streaming server and client connection. StereoDroid's work is planned as an upstream contribution to current ALVR. The relevant server and client paths checked were `alvr/server_openvr`, `alvr/client_core`, and `alvr/server_io`.

The contributors returned for those paths are Riccardo Zaglia, zmerp, zarik5, Max Thomas, Leonhard Saam, Meister1593, Harsha Raghu, Yury, Vixea, JellyfishKnight, Liu Han, Luca Schlecker, Mathew Tkachuk, Okabintaro, Romain Roffé, besauce, diekleinekuh, eyJhb, galister, 0forks, 20kdc, Alexey "Cave Johnson" Kolesnikov, Baptiste Lartigau, Barnaby, Deandre Thomas, E1int, HoLo85, Jarett Millard, Keegan Boldt, Ričards Šašalevičs, Stu Charlton, failboat78, skryvel, szneqz, vaughan, vdi, wsippel, yoyobuae, and 黯然销魂code. ALVR's README states that it is licensed under the MIT License.

## PhoneVR

[PhoneVR](https://github.com/PhoneVR-Developers/PhoneVR) is the planned Android headset client. Its README describes the ALVR mode as using the Google Cardboard API and names Alvr-org as the ALVR server developer. The contributors returned for `code/mobile/android/PhoneVR` and `code/common`, excluding the dependency bot, are Harsha Raghu, Rohit Panchal, ShootingKing-AM, thezofx, Nick, Riccardo Zaglia, and verypurple. The repository LICENSE is GNU GPL version 3.

## Cardboard SDK

The phone client is planned to use the [Cardboard SDK](https://github.com/googlevr/cardboard) for viewer calibration and lens support. Its README credits Google LLC. The full-history shortlog contributors are Phoenix Huang, xinyunh, Jared Finder, Javier Balloffet, Agustin Alba Chicar, and Fred Sauer. The repository LICENSE applies Apache License 2.0 to the SDK files except those covered by its Unity Companion License terms.

## SteamVR and OpenVR

StereoDroid will use Valve's [SteamVR](https://store.steampowered.com/app/250820/SteamVR/) runtime and the [OpenVR SDK](https://github.com/ValveSoftware/openvr) interface. OpenVR's README describes the SDK as an API and samples, with the runtime provided by SteamVR. The OpenVR repository credits Valve Corporation and its shortlog names Joe Ludwig, Jeremy Selan, Charles Lohr, Aaron Leiby, Alex Hopmann, Nat Brown, Dan Ginsburg, Gabe Rowe, Jeep Barnett, Keith Bradner, and Nathan Nuber. The OpenVR LICENSE is BSD 3-Clause. SteamVR runtime source is not part of the OpenVR SDK repository.

## Universal Media Server

The planned movie mode will allow [Universal Media Server](https://github.com/UniversalMediaServer/UniversalMediaServer) or another DLNA server to send a movie to the phone. Universal Media Server's README lists ik666, mik_s, SubJunk, SurfaceS, and valib as current project members. It thanks chocolateboy, ditlew, ExSport, happy.neko, infidel, js-kyle, Nadahar, Raptor399, Redlum, renszarv, SharkHunter, skeptical, taconaut, tcox, threedguru, and tomeko for major code contributions. Its LICENSE.txt is GNU GPL version 2.

UMS uses [jUPnP](https://github.com/jupnp/jupnp). It was also studied as an Android option; the implemented phone renderer uses pupnp instead. Its records credit Kai Kreuzer, Christian Bauer and the jUPnP and Cling contributors. Its project file declares CDDL-1.0.

## Sparky Stereo OS

Sparky Stereo OS's credits are in its [ATTRIBUTIONS.md](https://github.com/Sparky-OS/sparky-stereo-os/blob/main/ATTRIBUTIONS.md).

## Movie decoding and native UPnP

[AndroidX Media3](https://github.com/androidx/media), Apache-2.0, credits Google and the AndroidX Media3 contributors. It supplies local movie decoding and stereo extraction, including pull request #3439.

[pupnp](https://github.com/pupnp/pupnp), under its BSD three-clause COPYING, credits Intel Corporation, Rémi Turboult, Michel Pfeiffer and its contributors in README and THANKS. It supplies native SSDP, SOAP and GENA for the phone renderer and desktop discovery.

The [MediaServer:4 and MediaRenderer:3 specifications](https://openconnectivity.org/developer/specifications/upnp-resources/upnp/mediaserver4-and-mediarenderer3/) are credited to the UPnP Forum, Open Connectivity Foundation and Digital Living Network Alliance. Implementation proofs do not imply DLNA certification.

Checked 2026-10-11. The flat display and movie path have emulated proofs. Tracked StereoDroid work and physical-device qualification remain separate.

## Shared flat-display receiver

The common phone display work extends Fabian Druschke's KDE Connect [desktop !996](https://invent.kde.org/network/kdeconnect-kde/-/merge_requests/996) and [Android !673](https://invent.kde.org/network/kdeconnect-android/-/merge_requests/673), under KDE's GPL alternatives. It uses the same FreeRDP, KRdp, KPipeWire and KWin components credited in [Flat Headset](https://github.com/Sparky-OS/flat-headset/blob/master/ATTRIBUTIONS.md). The flat-display receiver is not the later ALVR/PhoneVR tracked client.

## Current ALVR migration and emulated proof (2026-10-12)

The migration continues Harsha Raghu's [PhoneVR PR #410](https://github.com/PhoneVR-Developers/PhoneVR/pull/410), pinned at `2a2ecf5ee9a8e49e35fcdaeb97b9488e0eb135fb`, against official ALVR `ebec107b7e5f81677fb9c631d239daf2110bf573`.
The continuation builds a matching x86_64 client/server and checks every captured eye pixel through startup, retained-frame reprojection and Activity pause/resume. It uses injected poses; physical sensors, ARM APKs, optics, game compatibility and device latency remain unqualified. The PhoneVR and ALVR developers retain credit for the transport, decoder and lifecycle this work extends.
Harsha Raghu's name comes from the PR commits' author records.

The following PC audio proposals credit PipeWire and libmysofa contributors, the MIT KEMAR dataset, Fons Adriaensen's AMB-Plugins (GPL-2.0-or-later), Richard W. E. Furse and Paul Barton-Davis for the LADSPA header (LGPL-2.1-or-later), and IEM/Graz and the IEM Plug-in Suite developers including SceneRotator author Daniel Rudrich (GPL-3.0-or-later).
The isolated measurements cover PipeWire control replay and an AMB impulse rotator; the IEM processor route and a continuously head-tracked multichannel mix remain proposals.
Names and licences come from the projects' own records and Debian copyright files.

## Launcher icon

The StereoDroid icon is original vector artwork by Sparky Stereo, by Daniel Ramos and partners.
Daniel Ramos directs the work; OpenAI GPT-6 Astra, through Codex, drew it, and Anthropic's Claude Sonnet, through Claude Code, integrated it (2026-10-14).
It carries no third-party badge and no Sparky logo.
The Oxygen icon theme (David Miller, David Vignoni, Johann Ollivier Lapeyre, Kenneth Wimer, Nuno Pinheiro and Riccardo Iaconelli, per Debian's copyright record) was a style reference only; no Oxygen artwork was copied.
The artwork is licensed CC-BY-SA-4.0 (Daniel's decision, 2026-10-14).
