---
description: Encoder options that can offer smooth playback
---

# Recommended OBS WHIP settings

OBS Studio v30 now has WHIP output, which can stream into VDO.Ninja. While there are a few limitations of using OBS Studio with VDO.Ninja directly, some H264 settings that have reported offered good results are the following:

* Rate Control: CRF
* CRF: 23
* Keyframe Interval: 1s
* Preset: Veryfast
* Profile: High
* Tune: Fastdecode (required for WebRTC playback)
* x264 Options: bframes=0 (required for WebRTC playback)

In some cases when using VDO.Ninja to view the WHIP video, adding [`&buffer=2500`](../advanced-settings/view-parameters/buffer.md) to the VDO.Ninja view link can further help reduce any lost of skipped frames, but at the cost of increased latency.\
\
While these above settings may not offer the lowest latency or CPU usage, please try them out before seeking support about issues you may be having. It's very easy to break things with bad settings.

{% hint style="warning" %}
OBS Studio does not yet have fully compatible WHIP support with VDO.Ninja, as it lacks the ability to perform NAT traversal. You can resolve this issue with my patched version of OBS in the mean time:\
\
[https://backup.vdo.ninja/OBS\_VDO\_Ninja.zip](https://backup.vdo.ninja/OBS_VDO_Ninja.zip) \[[source](https://github.com/steveseguin/obs-studio/)]
{% endhint %}

## How to view WHIP streams using VDO.Ninja

There's a guide here for those looking to go live from OBS to VDO.Ninja via WHIP

{% embed url="https://docs.vdo.ninja/guides/from-obs-to-vdo.ninja-using-whip" %}

If looking for alternatives to publishing into VDO.Ninja, consider checking out [Raspberry.Ninja](../updates/updates-raspberry.ninja.md) also, which supports a broad range of encoders, including AV1-AOM, Intel QuickSync, Raspberry Pis, Nvidia Jetson, and many other hardware and software options. Playback is smooth, with support for multiple viewers. Runs on most systems, including Linux and _Windows for Linux Subsystem_ (WSL).
