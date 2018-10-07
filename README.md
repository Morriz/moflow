# MoFlow

My iOS shortcuts, aka *workflows*.

## Introduction

I blogged a small bit [about shortcuts on my iD!OTZ blog](https://idiotz.nl/2018/10/06/ios-12-shortcuts-review/), and wanted to have a better way of sharing my shortcuts.
Ultimately, iOS 12 shortcut URLs serve html pages hosted at Apple's servers, that trigger your browser to open, starts javascript doing some introspection of the environment, which then requests the final payload, which is probably a plist file that gets executed by the iOS Shortcuts app. Until we get a transparent mechanism that extracts these plist files directly, I have chosen to just publish my shortcuts as links directly. As such no versioning of these.

### Shortcut *functions*

To make DRY use of the shortcut possibilities I started creating shortcut functions. I am using the following naming scheme for clarity:

* '>' in front of a name shows that the shortcut expects an input, either from sharing or clipboard.
* '>' at the end of a name shows that the shortcut is an input, and does not trigger any explicit action.

I built up the following functions so far:

* [Copy >](): Asks for dictation in English and copies to the clipboard.
* [Copy Dutch >](): Same but for Dutch input.
* [Get Input >](): Checks if there is input already, otherwise takes clipboard content.
* [> Get Addr Obj >](): Tries to extract an Address object from the input, which can contain multiple entries (the Apple Maps sharing gives both the title as the address). We prefer a Maps/Url object over the title Text object
* [> Get Location >](): Tries to get a Location object from the input. Will show a notification (with sound if no valid Location can be found). Will use first found.
* [Get Contact >](): Asks for dicatation of contact’s name and tries to return matching Contact objects (if multiple prompts for selection). Will show a notification (with sound if no matching Contact can be found).

These are used in the following:

### *Main* shortcuts

I spent quite some moments in my car lately, and am disappointed about Siri’s shortcomings when it comes to dictation in other languages and delegating results to other apps. So I created the following shortcuts:

* [> navigate With Waze](): Accessible from Apple Maps/text-selection sharing, or when a contact or address is found on the clipboard.
* [> Navigate With Google >](): Same but for Google Maps
* [Drive Home](): Drive home with Waze
* [Drive To Contact](): Drive to a contact with Waze. Uses ‘Get Contact >’

