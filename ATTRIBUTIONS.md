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

The phone's DLNA renderer is planned to use [jUPnP](https://github.com/jupnp/jupnp), the UPnP library Universal Media Server uses. Its records credit Kai Kreuzer, Christian Bauer and the jUPnP and Cling contributors. Its project file declares CDDL-1.0.

## Sparky Stereo OS

Sparky Stereo OS's credits are in its [ATTRIBUTIONS.md](https://github.com/Sparky-OS/sparky-stereo-os/blob/main/ATTRIBUTIONS.md).
