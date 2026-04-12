---
title: The Invisible Auction - How Advertising Technology Became a Surveillance Pipeline
date: 2026-03-31 12:00:00 -500
categories: [privacy]
tags: [RTB, Mobile]
---

# Introduction

A government official sits at a computer. On the screen is a detailed map. The official draws a rectangle around an area and several red dots appear within the perimeter. They zoom in and select one. A play button appears. After clicking it, the red dot begins to move — traveling down a highway, stopping at a gas station, pausing for two hours at a church, then reversing course before settling for eight hours at a residential address. The red dot represents the real-time movements of an American citizen's mobile phone.

![Mobile device surveillance dashboard](/assets/rtbapps/locatex.png)

At this point you may be wondering what film this is from. A James Bond thriller, perhaps, or a scene from the Bourne franchise?

It isn't a film. It is an actual commercial product — available to government officials, law enforcement agencies, and other parties — that can track the movements of any smartphone in the country. All with no warrant or judicial oversight of any kind.

In this article we will examine how these products source their data, how they allow law enforcement to systematically sidestep Fourth Amendment protections, and what we as citizens can do to defend ourselves.

# Commercialized Surveillance

Over the last decade, a multibillion-dollar industry of commercial surveillance has quietly metastasized in the background of everyday American life. Large data brokerages harvest personal data at extraordinary scale and sell it to anyone willing to pay. One of the largest customers is the United States government — which uses it to circumvent the very constitutional protections designed to keep it in check.

Not long ago, law enforcement was required to obtain a warrant before accessing a citizen's location data. That requirement has been effectively rendered optional — agencies can now bypass it entirely by purchasing the data directly from private brokers, or licensing a polished surveillance product built on top of it.

One product in this space is Locate X, built by a data brokerage called Babel Street. It aggregates location data from across the data broker ecosystem into a searchable surveillance dashboard (shown at the beginning of this article), and the platform's capabilities are straightforward and alarming:

- Geofencing: Draw a boundary around any location — an abortion clinic, a mosque, a protest — and retrieve every device detected inside it.
- Historical trace: Select a single device and replay all its recorded locations over time.
- Clustering: Identify where a device stops most frequently, revealing a person's home address, workplace, and daily routine.
- Cross-referencing: See which other devices were in the same place at the same time as a target — mapping social networks through physical proximity.

A 404 Media investigation [showed](https://www.404media.co/inside-the-u-s-government-bought-tool-that-can-track-phones-at-abortion-clinics/) exactly how this plays out in practice. Researchers used Locate X to track a device that traveled from Alabama — where abortion is now illegal — across state lines to a clinic in Florida. The tool displayed the device's home address, its full route, the approximately two-hour stop at the clinic, and the return journey home.

A competing product called Webloc, offered by a company called PenLink, provides a similar surveillance dashboard — and ICE recently [spent](https://www.eff.org/deeplinks/2026/01/ice-going-surveillance-shopping-spree) five million dollars in taxpayer money acquiring access to it.

Your taxpayer money. Used to purchase surveillance licenses. Built on your own data, extracted from your own phone, without your knowledge or consent.

So where does this data actually come from? The answer is both mundane and shocking: the advertising systems embedded inside the apps you use every day.

# How Tracking Works

Every time you open an app or visit a website with advertising, an invisible automated auction takes place in the milliseconds before the page finishes loading. This system is called Real-Time Bidding, or RTB.

Here's how it works:

1. You open an app or webpage. The publisher detects an open ad slot — a space where an advertisement can be shown to you right now.
2. A data packet called a bid request is broadcast simultaneously to every participant in the auction. At its core is your device's unique advertising ID — Apple calls this the IDFA (Identifier for Advertisers), Google calls it the GAID (Google Advertising ID), but they're collectively known as MAIDs, or mobile advertising IDs. The packet also includes your device model, operating system, the app you're using, the time of day, and your location — either precise GPS coordinates if the app has location permission, or an estimate derived from your IP address.
3. Each participant decides whether to bid, and how much, for the right to show you an ad. The highest bidder wins. Their ad loads on your screen. The whole process takes under 100 milliseconds.

As mentioned, the bid request doesn't go only to the winner — it goes to every participant at once. And not everyone in that pool is an advertiser. Some are data harvesters: companies that have inserted themselves into the RTB ecosystem purely to collect bid requests, extract the personal data inside them, and sell it. They often don't even bother placing a competitive bid. This technically violates RTB exchange rules, but enforcement is nearly nonexistent, and the profit motive is enormous.

This is how a company like Babel Street — and the brokers it buys from — quietly amass billions of location pings, each tied to a MAID, each MAID representing a single consistent device over time. With enough pings, you can reconstruct where any person has been, when, and how often. Feed that into a tool like Locate X, and you have a private surveillance apparatus more powerful than anyone could have dreamed of a generation ago.

Horrifyingly, an entire ecosystem of apps has emerged to feed this market. Apps like Freecash, which entice users to install by promising payment for playing games, make vast sums by harvesting your location data and selling it. Others started as legitimate products and were later co-opted. The Weather Channel app, for example, was [caught](https://www.theguardian.com/technology/2019/jan/04/weather-channel-app-lawsuit-location-data-selling) quietly selling users' precise location data to third parties.

It is a staggeringly pervasive problem. But there are things we can do to protect ourselves.

# How to Protect Yourself

This section covers practical steps you can take on two platforms: iOS and GrapheneOS. Both offer meaningful protections against the surveillance ecosystem described above.

## iOS

**1. Disable IDFA Tracking**

- `Settings → Privacy & Security → Tracking → toggle OFF "Allow Apps to Request to Track."` This prevents apps from accessing your IDFA entirely. When this is off, apps receive all-zeros instead of your real IDFA. This is stronger than resetting periodically.

- `Settings → Privacy & Security → Apple Advertising → toggle OFF "Personalized Ads."` This limits Apple's own use of your data for targeting within Apple's ecosystem.

**2. App Declutter**

Mobile applications are the *key* source of data fueling RTB-based surveillance so it is imperative you aggressively eliminate as many apps from your phone as possible. 

Look through all of your apps and delete each one that you haven't used in the last two weeks. (If you ever truly need it again in the future you can always re-install it in 30 seconds). 

For any apps you are hesitant about removing its worth quickly viewing their privacy policy in the App Store; if they state they track you across apps and websites this app certainly doesn't have a place on your phone.

![App policy of Tonies iOS app](/assets/rtbapps/toniapp.jpg)
_The AppStore privacy policy for the iOS Tonies Audiobook application._

>Warning: Don't just stop at deleting apps that show ads. Even if an app doesn't show ads it might still send your data off by virtue of software development kits (SDKs) - software the developer integrated into the code of the app itself that can send data directly to data brokers in the background.
{: .prompt-danger }

>Tip: Install apps as progressive web apps (PWAs). A PWA is a website designed to provide a similar experience to that of a mobile app installed from an App Store — saveable to your home screen, capable of sending notifications, and usable offline. Because it runs inside your browser rather than as an installed app, it cannot access your IDFA or embed hidden tracking SDKs. To install a PWA in Safari, tap the Share button → Add to Home Screen → Add. In Brave or other mobile browsers, tap the three-dot menu → Add to Home Screen → Install.
{: .prompt-tip }

![Installing PWA on iOS](/assets/rtbapps/pwa.jpg)
_Instructions for installing PWAs to iOS and Android mobile devices can be found [HERE](https://www.kasmweb.com/docs/develop/user_guide/pwa.html)_

**3. Audit App Permissions**

Conduct regular audits of the permissions apps have on your device, paying particular attention to location — this is what allows apps to include your precise GPS coordinates in RTB bid requests.

- Location: `Settings → Privacy & Security → Location Services`. Set every app to Never unless it genuinely requires location to function (a maps app, for example). For apps that do need it, select "While Using the App" rather than "Always."
- Other sensors: `Settings → Privacy & Security`. Review access for sensors like your camera and microphone and revoke anything that seems unnecessary.

**4. Use a VPN**

With location permissions disabled, the RTB process falls back on your IP address to estimate your location. While less precise than GPS, your IP address still places you within a specific region. Use a reputable VPN — Proton VPN and Mullvad are both strong options — to mask your real IP with one from a location of your choosing.

**5. Block Ads System-Wide**

Dismantling the data sources used in RTB goes a long way, but it's worth also blocking ads from loading in the first place.

- Install a privacy-friendly browser like [Brave](https://brave.com/), which blocks ads and trackers while browsing the internet. More information on privacy-friendly browsers can be found [HERE](https://kryptosis.xyz/posts/digitalprivacypyramid/).
- To block ads inside apps, use [NextDNS](https://nextdns.io/) to install a configuration profile on your device that automatically blocks connections to known ad and tracking domains system-wide. A full guide on setting this up is coming soon!


## GrapheneOS

GrapheneOS is a free, open-source, privacy-focused operating system built on Android and arguably the most secure mobile OS available.

It ships with several meaningful protections out of the box. There is no MAID on a base installation, eliminating the core identifier that powers the RTB pipeline. A system-wide sensor permission lets you block app access to hardware signals commonly used for device fingerprinting. And a per-app network toggle — absent on both stock Android and iOS — lets you install any app and cut off its internet access entirely.

Even with these defaults, there are additional steps worth taking:

**1. Use FOSS Apps**

Install apps through F-Droid or Obtainium. These sources carry free and open-source software, which is generally free of trackers and advertising SDKs. For apps that must come from the Google Play Store, use Aurora Store to install them anonymously.

**2. Disable Network Access for Apps That Don't Need It**

For any app with no legitimate reason to connect to the internet, revoke its network permission: `Settings → Apps → [App Name] → Permissions → Network → Don't Allow`.

**3. Isolate Google Play Services**

Some apps — such as banking apps — require Google Play Services to function. GrapheneOS offers a sandboxed version you can install deliberately, unlike stock Android where it is deeply embedded in the OS. And because it runs as just a regular app, you can manage its permissions directly.

However, installing Google Play Services generates a GAID that can be used for tracking. To delete it: `Settings → Apps → Sandboxed Google Play → Google Settings → All Services → Ads → Delete Advertising ID`.

To ensure maximum protection, you can run any apps that require Google Play Services in a separate device profile, which fully isolates them from the rest of your system.

**4. Use a VPN**

As with iOS, a VPN prevents regional location tracking by masking your real IP. Proton VPN and Mullvad are both solid choices.

**5. Block Advertisements System-Wide**
- Just like with iOS, install a privacy-respecting browser like Brave to blocks ads and trackers will browsing the internet. 
- Use NextDNS to block ads system-wide on your device. Go to Settings → Network & Internet → Private DNS and enter your NextDNS hostname for system-wide ad and tracker blocking.

# Conclusion

Short of going without a smartphone entirely, GrapheneOS represents the most secure and private experience you can have on a mobile device. If you're curious, you can learn more on their [website](https://grapheneos.org/). NBTV also has a fantastic introductory [video](https://odysee.com/@NaomiBrockwell:4/Graphene-Install:e) on how to install and set up a new GrapheneOS device.

For those who prefer iOS, you can still achieve meaningful protections against the surveillance apparatus that has quietly built up around us from the ouroboric relationship between corporations and the government.

That said, technical steps alone are not enough. Contact your local lawmakers and demand change — comprehensive privacy protections and real reform. Remind them that they are public servants and we are private citizens. They work for us.

If you found this helpful, share it with your friends and family. The more people who take these steps, the more we send a message: Privacy isn’t suspicious. It’s not for people with something to hide.

It’s a human right.

And it’s something we all deserve.