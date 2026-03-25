---
title: Digital Privacy Pyramid
date: 2026-01-27 12:00:00 -500
categories: [privacy]
tags: [browsers, vpns, tor, encryption]
---

## Introduction

The USDA recently released their new and updated food pyramid. You know - eat vegetables, limit sugars, all that good stuff.

Now, this isn't a nutrition blog. It's a digital privacy blog. 

But just like your body needs proper nutrition to stay healthy, your digital life needs foundational privacy practices to stay protected.

So I created the Digital Privacy Pyramid.

![A 3-level pyramid with privacy strategies](/assets/digitalprivacypyramid/pyramid.jpg)

Three levels with four simple changes. By the time you reach the top, you'll be remarkably protected against surveillance capitalism and the army of data brokers trying to profit from your personal information.

## Privacy-Respecting Browsers

Your browser is probably the most used application on your computer. Mine too. It's your window to the internet. You use it for work emails, social media, streaming, shopping—everything. But just as much as your browser provides a window to the internet, it might also provide a window into YOU. 

About 70% of internet users use Google Chrome as their browser. 

![Graph showing browser market share](/assets/digitalprivacypyramid/graph.jpg)

Now Chrome isn't free because Google is generous. It's free because YOU are the product. Google recently was valued at 4 trillion dollars. 70% of their income is from advertisements that they serve by creating detailed profiles through tracking their users.

Time to slam that window shut, and board it up.

Here are the best privacy-respecting browsers you can switch to today to regain control of YOUR data.

### [Brave](https://brave.com/) 

Brave is the easiest way to start using a privacy-respecting browser. Why? It's built on the same software as Chrome. So it behaves just like Chrome. I hear you. "Built on the same software as Chrome? Aren't we trying to get away from that?"

Let me explain.

Here's how Chrome gets made: Google starts with Chromium, which is open-source software. Then they layer on loads of proprietary code—the tracking, the profiling, all the surveillance stuff. 

Brave also starts with Chromium. But unlike Chrome, it doesn't include any of that proprietary Google code used to track you across the internet. In fact, Brave does the opposite. It includes built-in ad blocking, tracker blocking, and fingerprint-resistant technologies right out of the box.

Brave also includes some cool features such as encrypted video calls (think Google Meet replacement), a private AI assistant called Leo, and more. Of course all of this can be disabled if you want a more streamlined experience. But it's there if you want it.

### [Firefox](https://www.firefox.com/)

Of all the browsers on this list, Firefox is probably the one you've heard of.

Mozilla released it back in 2004, and it has since been a shining light for a private internet and digital rights. Unlike Brave, Firefox is built on Gecko, and so represents a break from the monopoly of Chromium.

Firefox has built-in ad and tracker blocking, fingerprint protections, and a host of other neat tricks like the Facebook Container that helps silo Facebook's pervasive tracking across the internet. And because Firefox is open source, developers have created tons of Firefox variants. Some are even more privacy-focused than the original, as you're about it see. 

For those who choose Firefox remember to change the default search engine from Google to something more privacy-respecting like DuckDuckGo.

> **Tip: Bang out a search** You can use a bang(!) to conduct a quick Google search without changing the default search engine. For example: `bears !g` will use the Google search engine for that one query.
{: .prompt-tip }    

### [Tor Browser](https://www.torproject.org/download/)

The Tor Browser is a hardened Firefox variant. It includes many built in protections, and most notably, it has the Tor network baked right in; the technology from which the browser gets its name. We will discuss the Tor network in detail later. For now, just understand it is an anonymizing network that sends your browsing through 3 different servers scattered across the world. This ensures no one knows who you are and what you are searching. 

An important note about the Tor browser: It is critical to not modify the browser in any way (except for adding bookmarks) so as to not give your browser a distinguishable fingerprint.

Fingerprinting is how companies identify you based on your browser's unique characteristics. Your screen resolution. Your installed fonts. Your timezone. Hundreds of tiny details that, combined, create a fingerprint as unique as the one on your thumb.

Where as Brave and Firefox block trackers and ads, they cannot protect your from sophisticated fingerprinting technologies. The only way to avoid standing out is to blend in completely. Tor makes your fingerprint identical to every other Tor Browser user. That's how it provides anonymity. But only if you don't customize it.

The moment you install an extension or change a setting, you stand out.

![Group of penguins with one that stands out](/assets/digitalprivacypyramid/penguins.png)
_Charlie added the Zoom extension to his Tor Browser. Don't be like Charlie._ 

### [Mullvad Browser](https://mullvad.net/en/browser)

Mullvad is another Firefox variant. Actually, you could say Mullvad is a Tor Browser variant, because that is, well, what it is. 

The Tor network provides anonymity by routing your traffic through no less than 3 nodes scattered across the globe.  This is great for anonymity, but bad for speed. Mullvad worked with the Tor Project to solve this. They created a browser with all of Tor Browser's privacy protections, but without the Tor network.

Instead, you use it with a VPN.

You get the anti-fingerprinting protection. You get the hardened security. But your connection runs at normal speed through your VPN instead of crawling through the Tor network. Just like Tor Browser, don't customize Mullvad Browser. Your fingerprint needs to be identical to every other Mullvad Browser user in the world. The moment you change something, you stand out.

## Encrypted Communications

At this point we are now surfing the web with a privacy-respecting browser.  No more ads following us around. No more sophisticated fingerprinting tracking our every move.

Now it's time for level two: encrypted communications.

Most of us do our communicating through email and messaging. And right now, those conversations are sitting on servers, unencrypted, ready to be scraped by AI and used to feed invasive profiles, or handed over to whatever government entity that asks nicely enough.

Time to roll up our encryption sleeves and fix this. Don't worry, it's easier than you think.

### Email: [Proton Mail](https://mail.proton.me/u/0/inbox) and [Tuta](https://tuta.com/)

Consider this: more than 121 billion emails go through Gmail every day.

Think about what's in those emails. Transaction receipts. Doctor appointment reminders. Heartfelt messages between family members. Subscription notifications. All of it sitting on Google's servers, now being ingested by Gemini. Now, Google will let you opt out of AI training. But you have to give up spell check, folders, and half the features that make email usable. In other words, no one is opting out. 

Instead use services like Proton Mail or Tuta. 

Both platforms provide full end-to-end encryption for your emails. That means even they can't read your messages. The encryption happens on your device before anything gets sent.

Proton even offers encrypted calendars, encrypted drive storage (think Google Drive replacement), collaborative docs and sheets, a password manager, an AI assistant, and soon Proton Meet—a Zoom replacement. In the past, privacy meant sacrificing usability. Not anymore. These platforms are robust, rich, and accessible to anyone.

It's like having your cake and eating it too. But privately, where no one's watching.

### Messaging: [Signal](https://signal.org/)

Texting via SMS is sent in clear text. Anyone with access to the network can intercept it.

Earlier this year, the FBI and CISA put out a joint recommendation to encrypt all your messaging communications. Why? China backed hacking group known as Salt Typhoon compromised the networks of AT&T, Verizon, and Lumen. They had access to real-time unencrypted calls and text messages. And it's not just foreign threats. The danger is domestic too. Remember when Snowden blew the lid off the NSA conducting bulk surveillance on every American's phone records?

Even Apple's iMessages, which are encrypted, have a backdoor: if you don't have Advanced Data Protection turned on, your backups aren't encrypted. And Apple has been handing data over to government requests at increasing rates.

Signal is a fantastic solution!

First off, it's cross-platform meaning you will be able to receive encrypted messaging synced across all your devices regardless if they iOS, Mac, Linux, Android, etc. File sharing. Video calls. All of it protected with end-to-end encryption goodness. 

Set up is super easy. Simply install the app and will be up and running in under five minutes. 

Your friends and family will also need to have Signal installed in order for you to communicate with which presents the only barrier. But honestly, odds are a lot of your contacts are already on it so you'll be chatting and one-uping each other with that perfect GIF in no time. 

## VPNs and Tor
### VPNs: [Mullvad VPN](https://mullvad.net/en) and [Proton VPN](https://protonvpn.com/)

VPNs are heavily misunderstood.

Here's how the internet normally works: Your requests go to your ISP, and your ISP forwards them to wherever you're trying to go. Your ISP can log everything you do. They can sell that data. And in many cases, they do.

A VPN encrypts your traffic before it leaves your device and sends it to a VPN server. The server decrypts it and sends it on. To the rest of the world, your traffic looks like it's coming from that server, not from you. This protects you against ISP surveillance and man-in-the-middle attacks on open networks. Businesses use VPNs every day to secure their networks. There's a reason for that.

Here's the catch: a VPN changes who you're trusting. That VPN server is now receiving all of your web requests. So you need to make sure you're using a "no-log" VPN provider that's actually trusted in the privacy community.

Two great options: Mullvad VPN and Proton VPN.

Take Mullvad. Simply download the app, click one button, and BOOM you have an account. No email. No identifying information. Just an account number. It costs about $5 a month and covers five devices.

Both have been audited. Both have proven track records. Both actually mean it when they say they don't log your activity.

What if you just don't want to trust anyone? There is an answer for you and it's...

### [Tor](https://www.torproject.org/)

Tor has already come up a few times in this blog? But what exactly is Tor?

Tor stands for "The Onion Router", and essentially works like three VPNs daisy-chained together.

When you visit a normal website (the "clearnet"), your traffic bounces through three random nodes before reaching its destination. Each node only knows the one before it and the one after it. No single node can see both where you're coming from and where you're going.

For sites on the dark web (onion services), it's even more secure. Your traffic goes through six nodes with a rendezvous point in the middle. This process ensures the anonymity of both the source and the destination; no one can determine the location of the person making the request, and no one can determine the location of the server on the other end. 

There's a narrative that Tor and the dark net are only for nefarious purposes.

That's wrong. 

Tor is an invaluable resource that keeps whistleblowers safe. Tor protects journalists. Tor gives people living under oppressive regimes a way to communicate freely. Heck, even Facebook has an onion site. As does the BBC and many other reputable sources. Even I have a site on the dark web. Want to see it?

Open up the Tor Browser and paste: http://mr4l45472srqdhqvnx5ujbvqeq43qibpdlr75z5l6d25wbmxawsjemyd.onion/

![A website showiing a joke](/assets/digitalprivacypyramid/joke.jpg)
_Okay, I was wrong. The dark web is only for miscreants because jokes this good have to be criminal._ 


## Conclusion

Look at what you've accomplished.

You're encrypting your communications like a pro. You're browsing without ads and trackers slowing you down. Your data isn't being scraped and sold to the highest bidder. That's a big deal.

I know this can seem like a lot, but please remember that privacy isn't a race. It's a slow, deliberate process. One step at a time. Just know that each step you take protects you from the people who see you as nothing more than a walking bag of data—something to be mined, analyzed, and sold off for profit.

All at your expense.

If you found this helpful, share it with your friends and family. The more people who take these steps, the more we send a message: Privacy isn't suspicious. It's not for people with something to hide.

It's a human right.

And it's something we all deserve in our future.