---
description: How to capture the (free) system Text to Speech audio in Windows with OBS
---

# Windows TTS Audio Capture Methods for OBS

While free text-to-speech options are nice, they come with a few annoying limitations and challenges, which we will discuss below. Solutions will be provided.

### Background

OBS Studio's browser source does not have the ability to capture system-level text-to-speech (TTS) audio. It is capable of capturing premium TTS options, such as those powered by Google Cloud, Speechify, or Elevenlabs, but it cannot do so using the free built-in-to-browser ones.  This is a limitation all browsers face when dealing with free TTS.\
\
Furthermore, not all browsers even support text-to-speech. Opera, Firefox, and others may lack them.

OBS Studio has a limited set of system-level TTS options, with Chrome offer some Google-powered options, and Edge support Microsoft-supported ones, along support for [Windows-installable TTS service pack add-ons](https://www.microsoft.com/en-us/download/details.aspx?id=27224). \
\
You can get a list of support text-to-speech languages that your browser supports at [https://vdo.ninja/tts](https://vdo.ninja/tts)

## How to capture the free TTS and get it into OBS Studio

### Method 1: Default Audio Route

```
1. Set Virtual Cable as Windows default output
   - Sound Settings > Output > Virtual Cable
2. OBS:
   - Add Audio Input Capture
   - Source: Virtual Cable
   - Monitor: Monitor Only
```

### Method 2: Windows 10 App Route

```
1. Sound Settings > App volume and device preferences
2. Find browser in list
3. Output: Virtual Cable
4. OBS setup same as Method 1
```

### Method 3: Windows 11 App Route

```
1. Settings > System > Sound > Volume Mixer
2. Locate browser
3. Output: Virtual Cable
4. OBS setup same as Method 1
```

### Method 4: Audio Router

```
1. Install Audio Router
2. Route browser to Virtual Cable
3. OBS setup same as Method 1
```

### Method 5: Voicemeeter

```
1. Install Voicemeeter
2. Set as Windows default output
3. Route:
   - Hardware out > speakers
   - Virtual out > OBS
4. OBS captures Voicemeeter output
```

### Testing

```
1. Play TTS
2. Check OBS meter
3. Verify system audio
4. Adjust levels if needed
```

### Alternatives

If these options do now work for you, there are paid options available, using Google Cloud, Elevenlabs, and Speechify. You can also try to self-deploy your own self-hosted open-source project that offers TTS for free, but that is out of scope for this article.

## Where is TTS used?

TTS is offered in[ Social Stream Ninja ](../steves-helper-apps/social-stream-ninja/)in several places, to read out messages from audiences. It is also offered by [CAPTION.Ninja](../steves-helper-apps/caption.ninja.md), which offers closed-captioning, transcription, and translation. Both offerings have premium and free TTS options.
