---
title: Configure transcription and captions for Teams meetings
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection: 
  - M365-collaboration
  - m365initiative-meetings
  - highpri
  - Tier1
ms.reviewer: nakulm
ms.date: 03/13/2023
search.appverid: MET150
ms.localizationpriority: high
f1.keywords:
- NOCSH
description: Learn how to configure transcription and caption policies for Teams meetings.
appliesto: 
  - Microsoft Teams
---

# Configure transcription and captions for Teams meetings

In Microsoft Teams, there's an option for meeting recordings to have automatic transcription, so that users can play back meeting recordings with closed captions and review important discussion items in the transcript. Transcription and captions help create inclusive content for viewers of all abilities.

## Transcription

This setting is a combination of a per-organizer and per-user policy. This setting controls whether captions and transcription features are available during playback of Teams meeting recordings. The person who started the recording needs this setting turned on for these features to work with their recording.

When transcription is turned on, users will have a written copy of the spoken text that is captured in near real time. After the meeting, users can find the searchable transcription stored with the meeting recording. And if transcription was turned on for the recording, Stream will play the video with the transcript next to the recording, showing who is speaking and when as the video plays. If recording is turned on but transcription is turned off, the the recording will not have a transcript file stored next to it and when viewing the recording playback in Stream, captions won't be able to be turned on.

This transcription link will remain for the lifetime of the file in most cases, but can be broken if the video file is copied within the same OneDrive or SharePoint site, which would result in captions not displaying on the copied video file.

> [!NOTE]
> Transcription for recorded meetings is currently only supported for English (US), English (Canada), English (India), English (UK), English (Australia), English (New Zealand), Arabic (United Arab Emirates), Arabic (Saudi Arabia), Chinese (Simplified, China), Chinese (Traditional, Hong Kong SAR), Chinese (Traditional, Taiwan), Czech (Czechia), Danish (Denmark), Dutch (Belgium), Dutch (Netherlands), French (Canada), French (France), Finnish (Finland), German (Germany), Greek (Greece), Hebrew (Israel), Hindi (India), Hungarian (Hungary), Italian (Italy), Japanese (Japan), Korean (Korea), Norwegian (Norway), Polish (Poland), Portuguese (Brazil), Portuguese (Portugal), Romanian (Romania), Russian (Russia), Slovak (Slovakia), Spanish (Mexico), Spanish (Spain), Swedish (Sweden), Thai (Thailand), Turkish (Turkey), Ukrainian (Ukraine), Vietnamese (Vietnam). The transcription is stored together with the meeting recordings in OneDrive and SharePoint storage.

> [!NOTE]
> Meeting transcription is not yet available in GCC.

### Use the Teams admin center to turn on or turn off transcription

In the Teams admin center, you can turn on or turn off the **Transcription** setting within a meeting policy located under **Meetings** > **Meeting policies**. This setting is off by default.

### Use PowerShell to turn on or turn off transcription

Using PowerShell, you can configure the `-AllowTranscription` setting in TeamsMeetingPolicy. To learn more, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowTranscription $True
```

For information on how your end users can use transcription, read [View live transcription in a Teams meeting](https://support.microsoft.com/office/dc1a8f23-2e20-4684-885e-2152e06a4a8b).

## Live captions

Teams can detect what’s said in a meeting and present real-time captions. And, if you've turned on the new meeting experience, your users' captions will include speaker attribution — so you'll see not only what's being said, but who's saying it and when.

This setting is a per-user policy and applies during a meeting. This setting controls whether the **Turn on live captions** option is available for the user to turn on or turn off automatically generated live captions in meetings that the user attends. These captions will not be saved alongside the video file.

:::image type="content" alt-text="This screenshot shows the menu initiated by selecting the ellipses icon. The option to Turn on live captions is highlighted." source="media/meeting-policies-live-captions.png" lightbox="media/meeting-policies-live-captions.png":::

| Setting value | Behavior |
|---|---|
| **Off, but organizers and co-organizers can turn them on** | Live captions aren't automatically turned on for the user during a meeting. The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on. This is the default setting. |
| **Off** | Live captions are disabled for the user during a meeting. The user doesn't have the option to turn them on. |

For information on how your end users can turn on live captions, read [Use live captions in a teams meeting](https://support.microsoft.com/office/4be2d304-f675-4b57-8347-cbd000a21260). For information on how your end users can do this in live events, read [Use live captions in a live event](https://support.microsoft.com/office/1d6778d4-6c65-4189-ab13-e2d77beb9e2a).

For information on how your meeting organizers can set up human-generated captions, read [Use CART captions in a Microsoft Teams meeting](https://support.microsoft.com/office/2dd889e8-32a8-4582-98b8-6c96cf14eb47).

### Live translated captions

> [!NOTE]
> This feature is temporarily available in public preview. After the preview, the meeting organizer must have a Teams Premium license for attendees to use live translated captions.

By default, live captions are displayed in the language that’s spoken during a meeting. Live translated captions allow your users to see captions translated into the language they’re most comfortable with.

To enable **Live translated captions**, **Live captions** must be set to **Off, but organizers and co-organizers can turn them on** in the Teams admin center. To turn off **Live translated captions**, set this to **Off**.

For information on how your end users can turn on live translated captions, read [Use live translated captions in a teams meeting](https://support.microsoft.com/office/4be2d304-f675-4b57-8347-cbd000a21260).

## Related topics

- [Teams meeting recording](meeting-recording.md)
- [Accessibility guide for Microsoft Teams Admins](accessibility-guide-admin.md)
- [Teams policies reference - Meetings](settings-policies-reference.md#meetings)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
