---
title: How to Back Up Your Proton Pass Passwords with KeePassXC
date: 2026-05-28 12:00:00 -500
categories: [privacy]
tags: [KeePassXC, Passwords, Proton Pass]
---

## Introduction

Password managers have become an essential tool for basic digital security hygiene. They allow you to create strong, unique passwords for every online service while only requiring you to remember one master password.

Cloud-based password managers like [Proton Pass](https://proton.me/pass) have grown tremendously popular and for good reason. Beyond storing passwords, they offer browser extensions that auto-fill your credentials, 1-click email alias creation, easy password sharing with friends and family, and reliable data protection. Since your data lives with a third-party provider, you don't have to worry about losing everything if your hard drive unexpectedly dies. 

That said, relying solely on the cloud comes with its own risks. What if your provider suffers an unexpected outage? What if your account gets suspended, or the company shuts down entirely? In any of these scenarios, you could find yourself locked out of your own passwords.

That's where today's guide comes in. We're going to back up your Proton Pass passwords, but not just by exporting a file and calling it a day. We're going to import them into KeePassXC, a free, open-source, local-only password manager, so you always have a secure, offline copy ready to go.

## Backing up your Proton Pass passwords with KeePassXC
### Steps:
**1. Download and install KeePassXC:** Head to [KeePassXC.org](https://keepassxc.org/) and download the version appropriate for your operating system. Installation is straightforward.

**2. Export your passwords from Proton Pass:** Log in to Proton Pass, click the Settings cog wheel, and select Export. Choose ZIP as the file format, click Export, and enter your Proton Pass password to confirm. A ZIP file will download to your computer.

![Proton Pass export menu](/assets/passwordbk/zipfile.png)

**3. Extract the ZIP file:** Navigate to your downloads folder and double-click the ZIP file to extract it. This creates a folder called Proton Pass containing a .json file — that's the file we'll import into KeePassXC.

![Image of unzipped file](/assets/passwordbk/jsonfile.jpg)

**4. Import into KeePassXC:** Open KeePassXC and select Import File. From the import options, choose Proton Pass (.json), browse to your extracted .json file, and click Continue. will we upload to KeePassXC

![KeepassXC Import screen](/assets/passwordbk/import.png)

**5. Review your passwords:** KeePassXC will display all the entries it's about to import. Once you've confirmed everything looks right, click Done.

**6. Name your database:** At the General Database Information screen, give your database a name — anything works (e.g., KeePassDB). Click Continue.

**7. Keep the default encryption settings:** The defaults on the Encryption Settings screen are strong and well-configured. Click Continue.

**8. Set your master password:** This is the password KeePassXC will ask for every time you open the database, so make it strong. You'll need to either memorize it or write it down and store it somewhere physically secure. Enter it twice, then click Done.

![KeepassXC Credential screen](/assets/passwordbk/password.jpg)

**9. Save your database:** Choose where you'd like to save your KeePassXC database file — it's just a single file you can place anywhere on your computer. Click Save, and your database is created. 

![Save KeePassXC database file](/assets/passwordbk/savelocation.jpg)

**You're Done!**

You'll now be inside your KeePassXC database with all of your entries imported. Double-click any entry to view its username, password, and any additional details.

When you're finished, click the lock icon in the top toolbar to secure the database. To access it again, simply navigate to where you saved the file, double-click it, enter your master password, and you're in.

## Conclusion

KeePassXC is a fantastic tool whether you want a fully local password manager or a reliable offline backup for your cloud-based one. Personally, I use both — and for my most sensitive accounts, KeePassXC is the only place those passwords live. Since your entire database is a single file, it's also trivially easy to back up to a USB drive for an extra layer of protection.

>**Tip:** KeePassXC is desktop-only, but there are excellent companion apps for mobile. On Android, check out KeePassDX. On iOS, KeePassium is the go-to choice. Both can open your KeePassXC database file, so your passwords are accessible across all your devices.
{: .prompt-tip }

If you found this helpful, share it with your friends and family. The more people who take these steps, the more we send a message: Privacy isn’t suspicious. It’s not for people with something to hide.

It’s a human right.

And it’s something we all deserve.