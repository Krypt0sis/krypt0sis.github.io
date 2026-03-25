---
title: What Happens to Everything You Tell an AI?
date: 2026-03-14 12:00:00 -500
categories: [privacy]
tags: [AI, LLM]
---

# Introduction

Think back to the most sensitive thing you've ever mentioned in a conversation with an AI.

Maybe it was a health scare you were researching late at night. A legal situation you needed help thinking through. A personal conflict you were trying to process. A business idea you hadn't told anyone about yet.

Now ask yourself: how do you feel about that interaction today?

If you're anything like me, you immediately start to cringe remembering some of those past interactions.
Let's not beat ourselves up over it. These tools are genuinely useful, and the privacy implications aren't exactly advertised on the homepage. But going forward, we owe it to ourselves to understand exactly what happens to the things we share with AI — and what we can do about it.

The AI landscape is evolving fast. Privacy is almost always an afterthought. That means we have to think about it first.

![Image of a computer user being survielled by AI](/assets/aiprivacy/aiprivacy.png)

# The Threat Landscape
There are three primary threats I see posed to individuals and businesses by the proprietary models of what I call the Big Four: OpenAI, Anthropic, xAI, and Google. Those threats are model training, data breaches, and government access. Let's take them one at a time.

## 1. Model Training
Unless you're operating under an enterprise license or a paid account and purposefully opt out, these companies are using your chat histories to train their models. This isn't speculation — it's right there in their privacy policies.

OpenAI states plainly: "We use this information to improve and develop our Services and conduct research, including using your Content to train our models."

This matters more than most people realize. It's not just that your words are stored somewhere in a database — it's that they may become part of how the model thinks. Part of what it knows. And that's a fundamentally different kind of exposure.

As privacy advocate [Naomi Brockwell](https://odysee.com/@NaomiBrockwell:4/Private-AI:f) puts it, "Once a model is trained on this data, there is no simple way to ensure the information doesn't show up as an answer to someone else's prompt."

## 2. Data Breaches
The private databases behind the Big Four are goldmines. Every major tech company has faced a breach at some point, and there's no reason to believe AI platforms are immune. But there's a second threat that doesn't make headlines — quieter, more deliberate, and arguably more invasive: the monetization of your behavioral data through advertising.

Every time you interact with an AI, you're producing something incredibly valuable — a window into how you think. Your questions, your concerns, your decisions, your patterns. Over time, these interactions build a detailed cognitive and behavioral profile. And that profile is worth a lot of money.

This isn't theoretical. OpenAI has already released [proposals](https://www.bleepingcomputer.com/news/artificial-intelligence/openai-is-reportedly-getting-ready-to-test-ads-in-chatgpt/) to introduce advertising for users on the Free and Go subscription tiers of ChatGPT.

Most of us have made peace with seeing ads online. A Nike banner here, a sponsored post there — annoying, but harmless enough. What hides behind that familiar annoyance, though, is a system called real-time bidding, and it's worth understanding exactly how it works.

Every ad you see online is the result of an auction. In the milliseconds between you loading a page and an ad appearing, dozens of companies have bid against each other for the right to show you something. But here's what most people don't know: before the auction starts, every participant receives a detailed dataset about you — drawn from those behavioral profiles. Your interests. Your political and religious leanings. Whether an algorithm has flagged you as someone predisposed to certain pharmaceutical dependencies, or classified you as a "soccer mom." In some cases, the GPS coordinates of your precise location.

Every bidder gets this data. Not just the winner — everyone.

This has created a heavily abused system. Many entities enter these auctions with no intention of winning. They participate purely to collect your data, which they then sell in bulk to data brokerages — and to the government. It's a practice that sidesteps Fourth Amendment protections entirely, allowing sensitive information like your location to be [purchased](https://www.404media.co/cbp-tapped-into-the-online-advertising-ecosystem-to-track-peoples-movements/) without a warrant, no court order required.


## 3. Government Access
Your chat histories with AI models are not private from the law. They are subject to warrants and subpoenas. They can be automatically flagged and referred to authorities based on content. And in some cases, they can become part of the public record.

A clear example of this came in a recent copyright case where a judge [ordered](https://thehill.com/opinion/judiciary/5413932-chatgpt-promised-to-forget-user-conversations-a-federal-court-ended-that/) OpenAI to preserve all ChatGPT logs — regardless of whether users had paid accounts with deletion features enabled. The promise of deleted histories didn't hold up in court. The logs existed, and the court wanted them.

This is the part that tends to surprise people the most. You can opt out of training, you can delete your history — but if a legal process demands those logs, the company's obligations to you become secondary to their obligations to the court.


# So What Do We Do About It?
I want to be clear: I'm not telling anyone to throw their AI tools in the trash. The utility these models provide is real, and abandoning them entirely isn't the answer. The answer is being intentional about how and where you use them. There are three categories of AI tools worth understanding: the Big Four themselves, AI intermediaries, and private LLMs. Each has a different privacy profile, and the right choice depends on what you're doing.


## The Big Four — With Precautions
OpenAI, Anthropic, xAI, and Google produce the most capable models available. Unfortunately, that capability can come at a cost to your digital privacy. Here's how to use them more safely right now.

### 1. Opt Out
Every major platform offers some version of opting out of training and history retention. It isn't an ironclad guarantee — but doing it en masse sends a message. Go into your settings and turn it off.

### 2. Sanitize Your Prompts
Don't feed these models personal information when you don't have to. If you're asking for help with a document, swap real names for placeholders. If you're working through a personal situation, abstract the details.

For simple prompts, this is easy. For larger documents, it's a nightmare to do manually. Using an open-source tool called Fabric, I've built a [prompt](https://github.com/Krypt0sis/FabricPatterns/blob/main/sanitize/system.md) that instructs an LLM to sanitize whatever you feed it — identifying personally identifiable information like names, phone numbers, addresses, and API keys, then replacing them with realistic but fake alternatives. Start your conversation by pasting in the sanitize prompt to one of the private LLM options at the end of this article, then hand it whatever you want cleaned: a paragraph, a bulleted list, a JSON file. It strips the sensitive material and hands you back a clean version ready to paste into whichever Big Four model you want to use for a richer analysis.

Here is an example. Let's pretend I start with:
>My name is James Hargrove and I live at 4821 Birchwood Lane, Austin TX 78702. My doctor, Dr. Patricia >Nguyen, just diagnosed me with early-stage Type 2 diabetes. I need help drafting a letter to my >employer's HR department explaining why I need a modified work schedule. My work email is >jhargrove@acmecorp.com and my employee ID is 84772.

After copying and pasting the sanitize prompt, I copy and paste that into a private LLM and receive the following as output:

>My name is Michael Thornton and I live at 2247 Elmcrest Drive, Denver CO 80203. My doctor, Dr. Sandra >Merritt, just diagnosed me with a chronic health condition. I need help drafting a letter to my  >employer's HR department explaining why I need a modified work schedule. My work email is m. >thornton@genericcorp.com and my employee ID is 53291.

### 3. Enroll With Alias Information
Signing up for an AI service asks for a lot of personal information. However, no one said that information has to be *your* information.

For generating random names, addresses, and birthdates on the fly, [fakepersongenerator.com](https://www.fakepersongenerator.com/) is your friend.

For email, use an alias service like [SimpleLogin](https://simplelogin.io/) — you generate a forwarding address, give that to the company instead of your real email, and any messages they send get forwarded to your real inbox. When you want them gone, just turn the alias off. If they get breached, your real address was never in their system.

For payment, use [Privacy.com](https://www.privacy.com/). It generates virtual cards that function as real Mastercards to any merchant, but carry no real name or address — meaning you can enter whatever you want at checkout. (I've written more about this in a previous [post](https://kryptosis.xyz/posts/privacycom/).)


## AI Intermediaries
This is a rapidly expanding space. AI intermediaries are privacy-respecting frontends that act as proxies between you and both Big Four and open-source models. They come in two flavors: chat-only tools and more full-featured platforms I call AI workstations.

### Chat-Only Intermediaries
Several browsers and search engines now build these tools in. Brave has its Leo assistant. Kagi has a built-in AI. But the one I keep coming back to is [Duck.ai](duck.ai).

Duck.ai is free, has a polished web interface, and lets you interact with Big Four models like Claude Haiku alongside a range of open-source alternatives. More importantly, it's built with privacy in mind. As a proxy, it strips identifying information like your IP address and mixes your queries into large volumes of other traffic. According to their privacy policy, they hold enterprise agreements with the Big Four specifically to prevent your queries from being used for model training.

### AI Workstations
If you need more than chat — image generation, video, advanced workflows — two platforms worth knowing are [Venice.ai](https://venice.ai/) and [NanoGPT](https://nano-gpt.com/).

Venice.ai requires nothing more than an email address to sign up, an alias works perfectly. It's freemium, with free models available and paid tiers for more advanced options. NanoGPT similarly acts as a frontend to a range of models, but adds a useful wrinkle: it accepts payment in privacy-friendly cryptocurrencies like Monero, meaning you can access powerful AI with more financial privacy.

## Private LLMs — Cloud and Local
For the highest privacy bar, you want a model that either runs in a genuinely private cloud environment or runs entirely on your own hardware.

### Private Cloud
The best option in this category right now is [Proton Lumo](https://lumo.proton.me/). Built by the team behind ProtonMail, it's fully private, supports features like organized project chats and web search, and integrates with Proton Drive for paid members. It also has a well-designed iOS and Android app.

### Local-Only Models
For the ultimate privacy guarantee, nothing beats running a model on your own hardware. The data never leaves your machine. You're not trusting anyone's privacy policy — because there is no third party.

If you're comfortable with the command line and Docker, [Ollama](https://www.ollama.com/) paired with [OpenWebUI](https://openwebui.com/) is a fantastic combination. It gives you a polished chat interface running entirely locally, with support for a wide range of open-source models.

If that sounds like too much, [LM Studio](https://lmstudio.ai/) takes most of the complexity out of the equation. It has a clean graphical interface, tells you what each model is designed for and whether it will run on your machine, and lets you start chatting in minutes. You can also use it to set up a local server so other applications on your computer can talk to the model directly.

A newer entry worth watching is [Ente's Ensu](https://ente.io/blog/ensu/) — a local-only model that runs entirely on your phone. It's still in its early days, but the direction is promising. 

# The AI Privacy Toolkit
Tools change. New options emerge constantly, and ones you've relied on can disappear overnight. So rather than hand you a list of apps and call it done, I want to leave you with a toolkit — a way of thinking that applies to whatever the landscape looks like when you're reading this. If you want to go even deeper on this, Josh from [All Things Secured](https://odysee.com/@AllThingsSecured:9/AI-Privacy-Guide_-4-Tools-%2B-8-Rules:a) has done excellent work in this space and is well worth your time.

## Assume Permanence
Treat everything you type into an AI as if it's permanent. Not because it always is, but because that assumption puts you in the right mindset.

Opt out of training whenever the option exists. Delete your histories. But don't rely on those actions alone to protect you — as the court case showed, the data can outlive your preferences. The real protection starts before you hit send.

## Match the Tool to the Risk
Everyone has a different threat model. What feels risky to one person might be trivial to another. But most of us can think about our AI use on a sliding scale from high-stakes to low-stakes — and choose our tools accordingly.

Working on a legal document like a will? That's high-stakes. Feed it to a local model on LM Studio. Just got a medical diagnosis and want to research it with something more powerful than what runs on your laptop? Use Duck.ai connected to an open-source model. General research with no personal details involved? A Big Four model is probably fine.

You can also chain tools together. Take that will document, run it through a local model with a sanitizing prompt to strip the personally identifiable information, then hand the cleaned version to Claude or GPT-4 for richer analysis. You get the power of the best models without handing them your actual life details.

## The Right Tool Can Still Hurt You
Using a privacy-friendly tool doesn't make you immune. It's entirely possible to do yourself more harm using Duck.ai carelessly than using ChatGPT methodically.

Duck.ai's protections are real — but they only go so far. If you connect it to a closed-source model and type in something genuinely sensitive, you've exposed that data to the model itself, regardless of what sits in front of it. The proxy can't protect you from your own inputs.

The tools matter. But at the end of the day, we are the only ones ultimately responsible for our own digital privacy. No privacy policy, enterprise agreement, or local model will save us from ourselves if we're not paying attention. Intentionality is the real toolkit.


# Conclusion
Every question you've ever asked a proprietary LLM was answered at a cost. Not always money — sometimes it was your data, your profile, your behavioral fingerprint, handed quietly to systems you may have never agreed to interact with.

That's not a reason to stop using these tools. It's a reason to use them with your eyes open.
Start with the easy wins: opt out of training, use an alias email when you sign up, sanitize your prompts when the stakes are high. Work up from there. Explore Duck.ai. Try a local model. Build the habit of asking yourself, before you hit send: does this tool match this moment?

Privacy isn't suspicious. It isn't something only people with something to hide care about. It's the reasonable expectation that your thoughts — even the ones you share with a machine at 2am trying to solve a problem — belong to you.

If you found this helpful, share it with your friends and family. The more people who take these steps, the more we send a message: Privacy isn't suspicious. It's not for people with something to hide.

It's a human right.

And it's something we all deserve.