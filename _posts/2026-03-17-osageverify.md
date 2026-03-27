---
title: They Sold You Child Safety. They Built a Surveillance Machine.
date: 2026-03-17 12:00:00 -500
categories: [privacy]
tags: [OS, Age Verification]
---

# Introduction 
Let's start by playing a game. Read the following conversation and try to guess what product is being discussed.

**Vendor:** "Hi there. I think you'll really like this. To proceed I'll just need to see your ID."

**User:** "Oh, that's okay. I've used this several times and never needed an ID."

**Vendor:** "Yes, but this is a product that really needs to be regulated. ID, please."

**User:** "Okay. I really need to use this. Here you go."

**Vendor:** "Thank you! You seem to be of the right age. Enjoy."

Alcohol? A prescription medication? A casino?

It's someone logging into their computer for the first time.

If that sounds far-fetched, pay attention: there is a wave of legislation moving through state capitals and Congress right now that is laying the groundwork for exactly this future. These laws are sold to the public as protecting children from online harm. Some of the people who wrote them may even believe that. But when you follow the money and read the fine print, a different picture emerges — one of corporate liability laundering, surveillance infrastructure, and a systematic attack on the open, privacy-respecting internet.

I want to walk you through what these laws actually do, who is really behind them, and what genuine solutions look like. Let's get into it.

![Child under the opressive infrastructure of Meta](/assets/ageverify/age.png)

## The threat: an age verification wave washing over the world
This didn't start in the United States. The push for mandatory online age verification began in the United Kingdom with the Online Safety Act of 2023, then quickly spread to Australia through 2024 amendments to their own Online Safety Act. Country after country followed suit, and the wave has now hit American shores hard.

In the US, we've seen a spate of app store age verification laws pass across several states such as Texas, Utah, and Louisiana. Recently, however, California took this concept further than anyone with [AB 1043](https://www.tomshardware.com/software/operating-systems/california-introduces-age-verification-law) — the Digital Age Assurance Act — which doesn't just target app stores. It requires every operating system, on every phone, tablet, and computer, to collect a user's age during account setup and then transmit that information in real time to any application that requests it. Colorado quickly followed with its own equivalent bill, [SB26-051](https://leg.colorado.gov/bills/SB26-051).

Here is what these laws actually mandate. At device setup, the OS asks for your age and places you into one of four brackets: under 13, 13–15, 16–17, or 18 and over. The OS must then maintain a real-time API — a live data feed — that broadcasts your age bracket to any installed or future application that requests it, every time that app is launched or downloaded. The applications must accept this signal and respond accordingly. Fail to comply, and both the OS provider and the app developer face fines of up to $7,500 per affected child per intentional violation.

These laws are sold as protecting children. But they don't just fail at that — they lay the foundation for something far more dangerous. Today the law only requires users to enter their age, not verify it. But the infrastructure is being built regardless. All it takes is one additional amendment to require that age be confirmed by face ID or government-issued photo ID. At that point, you need to prove your identity to use a computer — any computer. That is not a hypothetical dystopia. It is one legislative clause away. And a society in which access to information and digital tools can be gated by identity verification is a society with all the ingredients needed for the erosion of democracy.

### Why open source will bear the cost
Large companies like Apple, Google, and Microsoft have the engineering staff, financial resources, and centralized account systems to build compliance infrastructure. It will be expensive and annoying for them, but manageable.

For open-source operating systems, this is potentially catastrophic.

Linux distributions — Ubuntu, Debian, Arch, and hundreds of others — are often maintained by volunteers collaborating asynchronously across different countries. Some are built by a handful of people who have never met in person. When California issues a fine to a non-compliant OS provider, who exactly do they fine? The anonymous developer in Germany who submitted a patch last Tuesday? The code is open source and distributed freely online — what stops someone from downloading it, stripping out any compliance layer, and redistributing it? These laws set open-source operating systems, and all the personal privacy that comes with them, up for failure.

The same problem cascades to app developers. Many apps are made by a single person as a labor of love — a hobby project with no legal team and no compliance budget. Faced with liability exposure they cannot afford, most will simply close up shop. The result is a contraction of the independent app ecosystem in favor of the App Store and Google Play, handing more control to the very companies most expert at tracking and monetizing user behavior.

Let me give you a concrete example. Take two diet tracking apps: Waistline and Lose It! Waistline is free and open-source — no advertising, no data collection, no tracking. Your health data stays on your device. Lose It! is a polished, well-funded app that, as its App Store privacy label discloses, collects your health and fitness data, identifiers, and sensitive information — linked to your identity and used to track you across other apps and websites.

If age verification compliance costs force Waistline's developer to close up shop, users don't simply lose a free app. They migrate to Lose It! or something like it, and their health data enters the commercial pipeline — aggregated by data brokers with location data, purchase history, and demographic profiles, then sold to anyone willing to pay. That includes the federal government.

A March 2026 EFF [investigation](https://www.eff.org/deeplinks/2026/03/targeted-advertising-gives-your-location-government-just-ask-cbp) confirmed that Customs and Border Protection has been purchasing Americans' location data directly from the online advertising ecosystem — data harvested from ordinary apps like fitness trackers, weather tools, and dating services. The Supreme Court's 2018 Carpenter ruling established that the government generally needs a warrant to obtain location data. Agencies have successfully argued that simply purchasing it from a commercial broker doesn't count as a search. The Fourth Amendment can be sidestepped entirely by buying what private apps already harvested from your phone.

But the government is not the only buyer. The same data brokers selling to federal agencies sell to anyone — including people who want to find out where you live. In June 2025, Minnesota state Representative Melissa Hortman was murdered in her home alongside her husband by a gunman who used people-search sites to track down over 45 elected officials. Notebooks found in his car listed 11 different data broker websites with notes on what each one cost and what each one revealed. As data broker researcher Jeff Jockisch [said](https://therecord.media/alleged-killer-minnesota-lawmaker-data-brokers-list) afterward: "Data brokers get people killed every day — the problem is that cops just don't look for that as a methodology."

Legislation that systematically drives users from privacy-respecting apps toward data-harvesting commercial ones is not a neutral policy choice. It is actively expanding the infrastructure already being used to stalk and surveil — all while claiming to protect children.
 
### Who is really behind this legislation
Here is where the story takes a sharp turn.

In 2025, Meta spent a [record](https://tboteproject.com/git/hekate/attestation-findings) $26.3 million on federal lobbying — more than any other technology company — and deployed over 86 lobbyists across 45 states. That works out to roughly one lobbyist for every six members of Congress. But Meta doesn't just hire lobbyists in the hope of influencing legislation. In the context of age verification, they actually drafted and delivered it themselves. “A Meta lobbyist walked into a Louisiana legislator's office and handed him the actual legislative language for a bill that would require Apple and Google to verify the ages of every user on their platforms. And they're not just active in Louisiana with House Bill 570, which meta deployed 12 lobbyists in the state of Louisiana alone in order to pass the bill 99-0, which by the way goes into effect on July 1st of this year. Meta also hired over 40 lobbying firms to get bills drafted both at the federal level and state levels across the country. Meta has also funneled over $70 million in funds to different state level super PACs and advocacy groups like the Digital Childhood Alliance in an attempt to cover up the fact that Meta is actually the company that is funding all of these bills.” ([Mental Outlaw](https://odysee.com/@AlphaNerd:8/meta-spent-millions-to-push-the-new-age:0)).

Why would Meta invest this heavily in child safety legislation? The answer is: COPPA. The Children's Online Privacy Protection Act prohibits platforms from knowingly collecting data from users under 13. A lawsuit unsealed in 2023 [revealed](https://www.seegerweiss.com/news/unsealed-complaint-reveals-meta-platforms-received-over-1-1-million-reports-of-users-under-the-age-of-13/) Meta had received over 1.1 million internal reports of users under 13 since 2019 — a potential liability estimated at over $50 billion.

The key word is "knowingly." The App Store Accountability Act and its state-level analogs include explicit provisions stating that developers who "relied in good faith on age category" data received from an app store are not liable. If these laws pass, Meta can point to the age signal received from Apple or Google and claim it had no independent knowledge a user was 12. The $50 billion exposure evaporates. The OS and the app store absorb the compliance cost. Meta walks away clean — and continues targeting minors with the blessing of a good-faith defense.

Critically, the bills impose no new requirements on social media platforms themselves — only on the app stores and operating systems that distribute all software, including their competitors'. Every confirmed supporter of these laws runs a social media platform that benefits from the liability shift. Every confirmed opponent runs an app store that bears the compliance burden. Child safety is the framing. Corporate liability laundering is the substance.
  

## Real Solutions for Real Problems
We must not let these forces of surveillance — and the pursuit of quarterly profits at all costs — erode our ability to freely access computers and information. These laws gain ground because they are sold to the public and to lawmakers as necessary to protect children from pornography, predators, and screen addiction. To be clear: these are real issues. Screen addiction is real and it impacts all of us. [Half](https://safecomputing.umich.edu/events/privacy/dr-lauren-girouard) of all US children between the ages of 10–12 now have social media accounts. These problems deserve serious attention and serious solutions. What's being proposed is neither.

Here is what genuine solutions actually look like — and what you can do right now.

### Fund independent research and digital citizenship education: 
Companies like [Common Sense Media](https://www.commonsensemedia.org/) are doing important work helping parents and kids navigate the digital world responsibly. We should go further. What if Congress passed bills designating real money to bring together researchers, child psychologists, and educators to study the actual effects of screen time and social media on children, and then used those findings to develop high-quality digital citizenship curriculum for schools and resources for parents? Equip parents and kids with real tools and real knowledge. That would do more for child safety than any age verification mandate.

### Push back against the addiction machine: 
Facebook and its peers have spent millions becoming psychological hackers. They studied what casino designers have known for decades and built the same mechanics into social media: the pull-to-refresh gesture mimics a slot machine lever, the notification badge is engineered to trigger anxiety, the infinite scroll has no natural stopping point. But the deepest hook isn't the interface — it's the feed itself. Facebook decides which posts you see, in what order, and how prominently, based entirely on what keeps you scrolling longest. Outrage keeps you reading. Tribal anger keeps you commenting. None of this is accidental. The partisan division tearing our country apart isn't a side effect. It's an engagement strategy.

Here are ways to push back.

- **Remove Facebook from your phone:** Consider this: in 2012, when Facebook first introduced mobile ads, they made up 14% of total ad revenue. By 2017 that figure was 88%. By 2025, 94% ([Digital Minimalism](https://www.penguinrandomhouse.com/books/575667/digital-minimalism-by-cal-newport/)). Facebook now earns more than 97.5% of all revenue from advertising — meaning close to 92% of all company revenue comes purely from keeping eyeballs on their mobile app. It's no secret why this works: our phones are always with us, and the app was purpose-built to make sure that in any spare moment of boredom, opening it feels inevitable.
The fix is simple: delete the app and use Facebook only in a desktop browser. For additional protection, use a dedicated browser or browser profile to prevent Facebook from tracking you across the rest of the web. You'll keep the same utility — but your usage will naturally drop. The average user currently spends close to 6 hours per week on Meta's mobile apps. If we collectively brought that down to 4 hours, Meta's earnings would fall by 33% — $54 billion dollars. Imagine what a message this would send! 

- **Move toward decentralized alternatives:** Platforms like Bluesky and Mastodon offer something the major networks have deliberately engineered away: a simple chronological feed of posts from people you actually chose to follow. No algorithm deciding what enrages you most. No psychological profiling. What you see is what the people you follow actually said, in the order they said it. Every post gets equal footing. It's a fundamentally different experience — and a reminder that social media doesn't have to work the way Facebook wants you to think it does.

- **Demand accountability from your lawmakers:** Meta knew about over 1.1 million underage users and bought legislation rather than change their behavior. Contact your representatives and demand they hold these companies accountable directly. We also need comprehensive federal privacy legislation with real teeth: the right to know what data is being collected about you, the right to delete it, and the right to opt out of its sale. Data brokers should be shut down entirely. The people-search sites that enabled the murder of a Minnesota lawmaker and the ad-tech pipeline that lets federal agencies buy location data without a warrant are not inevitable features of the internet. They are regulatory failures — and they can be ended.

None of these solutions require building a surveillance layer into the operating system of every computer in America. None of them require a solo app developer to integrate a government-mandated compliance API under threat of ruinous fines. And none of them hand Meta a $50 billion liability shield while making everyone else pay for it.

# Conclusion: Don't let them build the cage
We are at an inflection point. The laws being written right now will shape the architecture of the internet for decades. And the forces pushing the most dangerous ones are not doing it out of concern for your children. They are doing it because they face tens of billions in liability for years of knowingly exploiting children. Rather than simply choosing to stop abusing children, they found it to be more profitable to just buy legislation that makes someone else responsible.

The internet is one of the most important tools for human freedom, communication, and self-determination ever created. But that potential is under serious threat — not just from authoritarian governments, but from the private companies that have built engagement machines optimized for division and addiction, and from the lobbyists who are now trying to use child safety as a Trojan horse for surveillance infrastructure.

The good news is that the solutions exist. We know what a healthy, user-directed feed looks like — Mastodon shows us every day. We know how to fund research and education rather than build surveillance pipes. We know how to draw a line in Section 230 that protects the open internet while ending immunity for algorithmic manipulation.

What we need is for people to understand what is actually happening — who is behind these laws, what they actually build, and what genuine alternatives look like. The cage is being assembled quietly, one "child safety" bill at a time. The time to push back is now, before the last bolt is tightened.

Privacy isn't suspicious. It isn't something only people with something to hide care about. It's the reasonable expectation that your thoughts — even the ones you share with a machine at 2am trying to solve a problem — belong to you.

If you found this helpful, share it with your friends and family. The more people who take these steps, the more we send a message: Privacy isn't suspicious. It's not for people with something to hide.

It's a human right.

And it's something we all deserve.