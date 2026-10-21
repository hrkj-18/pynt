# NoZ Privacy Policy

**Effective date:** 20 October 2026

NoZ is an Android alarm, timer, reminder, calendar, and wake-up challenge app
developed by Pynt Labs. This policy explains information handled by NoZ and by
the services integrated with it.

**Privacy contact:** [1997harsh.jain@gmail.com](mailto:1997harsh.jain@gmail.com)

## At a glance

- NoZ has no user-account system and no NoZ-operated application backend.
- Alarm, reminder, timer, stopwatch, calendar, challenge, and sound data is
  stored in app-private storage on your device. NoZ does not upload that
  content to a NoZ server.
- NoZ includes Google Mobile Ads and Google's User Messaging Platform (UMP).
  Those services can process advertising, device, interaction, and diagnostic
  information as described below.
- Google Play processes subscription purchases. All NoZ features are free; an
  active subscription removes advertisements only.
- NoZ passes reminder text to the Android Text-to-Speech engine selected on
  your device. That engine may be supplied by Google or another provider and
  may have its own network and privacy behavior.

## Information handled by NoZ

### Information stored on your device

NoZ stores information needed to provide features you choose to use:

| Feature | Information | Where and why |
| --- | --- | --- |
| Alarms and wake-up challenges | Alarm time, repeat days, label, enabled state, challenge type and settings, snooze duration, vibration choice, sound selection, and delivery status | Stored in app-private local databases and preferences to schedule and manage alarms and playback. |
| Reminders | Title, optional notes, spoken text, schedule, enabled state, sound selection, vibration setting, and delivery status | Stored locally to schedule reminders and provide their playback. Reminder text is passed to the Android Text-to-Speech engine when spoken. |
| Timer and Stopwatch | Timer duration and status, elapsed or remaining time, deadlines, and stopwatch state | Stored locally so the app can restore or update these features. |
| Calendar | Names and identifiers of visible calendars, event identifiers, titles, descriptions, dates, times, and all-day status for the date range you request | Read from the Android calendar provider with your permission and stored in NoZ's local calendar database for display. NoZ does not edit provider events or turn them into alarms or reminders. |
| QR challenge | Camera frames while scanning and the scanned value while registering or checking a code | The scanner processes camera input to read a QR value. NoZ stores a SHA-256 digest of the registered value, not the raw value or a saved camera image. The raw value is handled in memory while the challenge runs. |
| Custom sounds | The audio file you choose and its display name | The Android file picker lets you select an MP3, WAV, or OGG file. NoZ copies the selected audio into app-private storage for playback; NoZ does not upload the file to a NoZ server. |
| Preferences and operation | Theme choice, permission history, schedule identifiers and times, challenge progress, and the last store-confirmed ad-removal status | Stored in local databases or Android app preferences to restore settings and coordinate app features. |

You may enter personal or sensitive content in alarm labels, reminder notes,
spoken reminder text, calendar descriptions, or QR codes. Do not put
information into these fields that you do not want stored on the device or
shown to someone with access to the device.

NoZ writes operational messages to Android's logging facilities, including
some alarm or reminder identifiers, schedule times, and error details. The
app does not include a dedicated analytics or crash-reporting service that
sends these logs to a NoZ server. Android system diagnostics or reports that
you choose to share are governed by Android and the relevant provider.

### Advertising and consent services

NoZ integrates Google Mobile Ads and UMP. Google documents that the Google
Mobile Ads SDK can automatically collect and share information such as:

- IP address, which may be used to estimate general location;
- advertising, app-set, and other device or account identifiers, where
  available;
- app and ad interactions, such as app launches, taps, and ad views; and
- diagnostic information about SDK and app performance.

Google processes this information for advertising, analytics, and fraud
prevention. The exact data and ad treatment can vary with the SDK version,
Google services, your region, consent choices, and any advertising features
enabled for the app. NoZ does not request precise device location. The
Google Mobile Ads SDK may infer general location from network information.

UMP updates consent information, presents a consent form when Google says one
is required, and reports whether an ad request is permitted. NoZ checks
`canRequestAds()` before requesting an ad. You can open **Ad removal &
privacy** in NoZ to review ad consent and, where Google says it is required,
open privacy options. You can also reset or delete the Android advertising ID
in Android settings. Google's current guidance is available in its
[Google Mobile Ads SDK Data safety disclosure](https://developers.google.com/admob/android/privacy/play-data-disclosure),
[UMP privacy documentation](https://developers.google.com/admob/flutter/privacy),
[Google Privacy Policy](https://policies.google.com/privacy), and
[advertising ID guidance](https://support.google.com/googleplay/android-developer/answer/6048248?hl=en).

Advertisements may appear in the Alarm list and on idle or paused Timer and
Stopwatch screens. No ads appear on active alarm-ringing or challenge screens.
Ads are not required to use any NoZ feature. An active Google Play subscription
removes ads only; all app features remain free.

Google or advertising partners configured by the publisher may provide or
measure ads. NoZ's source does not include a separate third-party ad
mediation SDK; any mediation or additional ad-network configuration in the
publisher's AdMob account is governed by those providers' notices and must
also be reflected in the applicable disclosures.

### Google Play Billing

If you buy the ad-removal subscription, Google Play processes the purchase and
payment. NoZ receives purchase and subscription status from Google Play to
determine whether ads should be shown. NoZ does not receive your payment card
details and does not operate a purchase-validation server.

NoZ stores a local copy of the last store-confirmed ad-removal status. While
Google Play is unavailable, the app may continue to honor the last confirmed
active status until a later successful refresh. NoZ refreshes subscription status when the app starts or resumes, after
purchase-related updates, when a validated internet connection returns, or
when you request a refresh; restoring purchases also queries Google Play. The
refresh depends on Google Play and network availability. Google Play controls
payment, renewal, cancellation, refund, and subscription state. See
[Google Play Billing](https://developer.android.com/google/play/billing) and
[Google Play's Terms of Service](https://play.google.com/about/play-terms/).

### Camera and QR scanning

Camera access is used when you choose to register or complete a QR challenge.
The app uses the bundled Google ML Kit barcode-scanning model to decode QR
values on the device. The source code contains no camera-image upload path.
NoZ stores only a SHA-256 digest of the registered QR value; it does not save
the raw scanned content or camera image. Google describes the
[Android barcode-scanning API](https://developers.google.com/ml-kit/vision/barcode-scanning/android)
and its bundled and dynamically downloaded model options. The installed
NoZ configuration uses the bundled model by default.

### Calendar

If you grant calendar permission, NoZ reads visible calendars and event
details for the date range you select. The event information is passed from
Android to NoZ and stored locally for display. NoZ does not write, edit, or
delete events in your calendar provider, and calendar events do not create
alarm or reminder deliveries. Calendar accounts and synchronization are
managed by Android and the calendar provider you use.

### Text-to-Speech

For spoken reminders, NoZ passes the text you entered to Android's default
Text-to-Speech engine. NoZ does not select a specific engine, receive a copy
of the generated speech, or control whether the engine uses an on-device or
network-based voice. Depending on the engine and your settings, spoken text
may be processed by that engine's provider. Review the privacy terms and
settings for the engine installed on your device. Android documents its
[TextToSpeech API](https://developer.android.com/reference/android/speech/tts/TextToSpeech).

## Permissions and Android services

NoZ uses Android permissions and services for the feature you choose:

- **Camera:** QR challenge scanning.
- **Read calendar:** reading visible device-calendar events after you grant
  access.
- **Notifications:** alarm, reminder, and timer presentation, subject to
  Android notification settings.
- **Exact alarms and full-screen intent:** time-sensitive alarm and reminder
  scheduling and, when Android permits it, full-screen alarm presentation.
- **Boot recovery, vibration, wake lock, and media playback foreground
  service:** restoring schedules and operating alarm or reminder playback.
- **Internet and network state:** required by advertising and Google Play
  services; the app itself has no NoZ-operated network API or backend.

Android controls permission grants, notification visibility, background
execution, backups, and system service behavior. Denying a permission or
changing a system setting can limit the corresponding feature.

The current alarm foreground notification can show the custom alarm label as
its title and is marked public by the app. A reminder notification uses the
reminder title with a generic body; a timer completion notification uses
generic text. Android's lock-screen and notification settings determine what
is actually visible. Avoid putting sensitive information in an alarm label
or reminder title.

## How information is used and the basis for processing

NoZ uses local information to provide the alarms, reminders, challenges,
calendar display, timer, stopwatch, and sound features that you choose. Google
Mobile Ads and UMP use information as described in Google's disclosures to
manage consent, deliver or measure advertising, and protect their services.
Google Play uses purchase information to process and administer a
subscription.

Where applicable law requires consent for advertising, UMP provides the
relevant consent choices and NoZ requests ads only when UMP reports that
requests are permitted. Google and other providers determine their own
processing purposes and legal bases under their policies. Legal requirements
vary by location.

## Storage, retention, and deletion

Alarm, reminder, timer, stopwatch, calendar, challenge, and custom-sound data
is kept in app-private storage until you delete the relevant item, clear NoZ's
app storage, or uninstall the app. NoZ does not set a separate remote
retention period for this local information because it does not keep a
NoZ-operated server copy. Android device backup and restore behavior depends
on Android and your device settings; NoZ does not operate a separate cloud
backup service.

You can delete alarms, reminders, and local calendar entries in the app.
Unused imported custom sound files are removed by the app when no saved item
references them. Clearing app storage or uninstalling removes local app data,
subject to Android backup or restore behavior. Uninstalling NoZ does not
cancel a Google Play subscription. Google Play and other providers may retain
their own purchase, consent, advertising, or diagnostic records under their
policies.

NoZ does not have user accounts or a remote account database to delete. For
help with information stored by NoZ, contact us. For information held by
Google, an Android calendar provider, or a Text-to-Speech provider, use that
provider's privacy controls or contact it directly.

## Security

NoZ stores local records in Android app-private databases, preferences, and
files. The app does not add a separate encryption layer to its SQLite
databases or preference values. Android's app sandbox and device security
settings provide platform protections, but no storage method can protect
information on a compromised, shared, or unlocked device. Notifications and
device backups may expose information depending on your system settings.
Google states that data collected by the Google Mobile Ads SDK is encrypted
in transit; that statement does not apply to all NoZ data or other providers.

## Children

NoZ does not ask for your age and does not create user accounts. It is a
general-purpose alarm and reminder app. Information entered in the app is
handled as described in this policy regardless of who uses the device.
Advertising and consent treatment may also depend on Google Play, AdMob, and
app-audience settings. Parents or guardians with a concern about a child's
information may contact Pynt Labs at the address below.

## International processing and your choices

Google Play, Google Mobile Ads, UMP, Android services, calendar providers,
and the installed Text-to-Speech engine may process information under their
own terms and in the locations where they or their service providers operate.
Review their notices for information about international transfers and
available privacy controls.

Depending on where you live, you may have rights to access, correct, delete,
restrict, object to, or receive certain personal information, and to withdraw
consent where processing relies on consent. You can delete local app records
using the controls above and manage ad consent in NoZ's **Ad removal &
privacy** screen. Contact us for requests relating to NoZ. We may need to
direct you to a third-party provider for information that provider controls.

## Changes and contact

We may update this policy when NoZ's features, SDKs, or legal requirements
change. The effective date at the top will be updated when a revised policy
is published. Check the policy linked from NoZ and its Google Play listing
for the current version.

**Pynt Labs**  
Privacy contact: [1997harsh.jain@gmail.com](mailto:1997harsh.jain@gmail.com)
