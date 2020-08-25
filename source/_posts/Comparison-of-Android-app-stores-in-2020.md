---
title: Android App Distribution in 2020
date: 2020-07-30 21:18:07
tags: ['android', 'deployment', 'APK', 'Google Play', 'infosec']
thumbnail: /gallery/thumbnails/header.png
toc: true
categories:
- dev
- android
---
# Play Store? Huawei AppGallery? Custom updater?
This article aims to answer common questions about the possibilities of android app distribution. I try to compare various ways of installation which can be interesting for non-public apps. I also examine relevant app stores to summarize their possibilities and limitations. The monetization, advertisement, and related business aspects are taken just briefly. Beware - the market situation is taken from the US/EU viewpoint. The regional situation in Russia, China, or India is beyond my knowledge.

<!-- more -->

As of 2020, there exist many app stores and other ways of app (APK) installation. On the other hand, there are not many full-fledged solutions available. It is quite easy to distribute an app on its own, yet dealing with further updates or the monetization narrows down these options to only a few big houses. The obligatory choice is still Google Play, which provides the most complete services to manage an app's distribution. With some drawbacks, there is also Samsung's Galaxy App Store, Huawei's AppGallery, Xiaomi's GetApps, and Amazon's AppStore. These come pre-installed on devices while alternative stores have to be installed manually.

## FAQ

People often ask these questions. Some of them will be answered further down the article.

### Is it possible to distribute an app outside of any app store?
Yes. An APK can be placed anywhere and installed once the user enables Install from Unknown Sources. Play Store (or any other store) can even take care of updates later - once there is a newer package uploaded in its repository.

### Can we develop a custom updater or app store?
Yes. Custom updaters are often offered by third-party app stores. Epic successfully distributed Fortnite (see [1](https://techcrunch.com/2018/09/07/fortnite-hits-15-million-installs-on-android/?guccounter=1&guce_referrer=aHR0cHM6Ly9uZXdzLnljb21iaW5hdG9yLmNvbS8&guce_referrer_sig=AQAAACRvmvDp_QEkxeLSrF_Mgxnf-z6x4Qd53T5QPQDcgS4EhL7pspZ3fL5epJNN-IcygCfwDExuEQPXoRp3LzJyLONbM5dQmDGHZwALkIeWCjrP6qi4AbOdVk6Bv0bfQ9gfNdMN0pHhSJs1BjTLYE5P5oPYFoKYRDNS8UT-adGw0mDM), [2](https://www.epicgames.com/fortnite/en-US/mobile/android/get-started)) with its own installer so they could avoid a 30% payment cut required by Google.

### How is Android app distribution different from Apple's App Store?
Apple used to restrict installation to only the official App Store. Nowadays, you can install the PWA app from the browser, but there are rumors Apple's going to greatly limit these and prefer native apps (see this [thread](https://news.ycombinator.com/item?id=23676109)). As they claim in submission guidelines: Apps that are not very useful, unique, are simply web sites bundled as Apps, or do not provide any lasting entertainment value may be rejected.

### Can an app auto-update itself?
Generally speaking: no. However, limited choices do exist. PWA apps wrapped inside WebView are commonly used. App's static assets (mp3, images, text, game levels, ...) can be distributed via Google Play through Play Store's auto-update routine or loaded from a custom server.

### Is it possible to distribute an app privately?
Yes, an APK can be distributed privately via Play Store to (1) selected organization (company, school, ...) which devices' accounts are part of organization's G Suite), (2) closed group of Google accounts (simple, yet limited to approx. 2000 users). An enterprise distribution is briefly <a href="#emm">covered here</a>. Sharing bare APK files is also an option, but this way is more prone to intellectual property leakage as well as an additional hassle with updates.

### Is it safe to distribute an APK by email?
No. APK file can be easily harmed. Gmail prohibits sending APKs, additionally, email extension size is usually limited to 4 MB (Gmail is not),  which is not enough for regular APK.

Cons:
* no APK update management
* issues caused by antivirus SW reporting unknown binary files
* no integrity checks
* user can't verify APK's origin

### Is an APK safe against piracy?
No. APKs are commonly pirated and shared on alternative/shady app stores. Hardcoded keys can be extracted and input fields (passwords) spoofed. Sensitive apps should be properly audited and possibly enhanced with some sort of runtime application self-protection. Delivering optimal security at a reasonable cost is a concern of risk management. If you are unsure whether you may be hacked, always remember the rule of thumb: Risk is related with vulnerabilities, which threaten (1) confidentiality (not disclosing sensitive information), (2) integrity (preserving the state of the system), and (3) availability (we do want our systems to be up and running) of the assets. This is also known as CIA Triad.

# Noteworthy Google Play alternatives
Third-party alternative app stores have to be installed by the user manually. Amazon's, Huawei's and Samsung's store are unavailable on the Play Store.

They usually can deliver updates automatically, but the user is required to confirm each installation/update through the system's package installer on their first run. Moreover, each app that can initiate APK's installation has to be firstly confirmed by the user as a trustworthy installer. Both of these limitations present a serious obstacle for many nontechnical users and can drive them away.

## Huawei AppGallery
AppGallery is one of the most advanced alternatives. It comes preinstalled on Huawei and Honor devices. Its installer is available through AppGallery's homepage for other devices as well. In the first run, the user is prompted to install HMS (whopping 93 MB).

Since [last year's ban](https://www.cnet.com/news/huawei-ban-full-timeline-us-restrictions-china-trump-executive-order-no-1-phone-maker-samsung/), Huawei got in a cumbersome situation. While finally being no. 1 smartphone manufacturer they effectively lost the western market due to the unavailability of Google Play Services (incl. Play Store). This leads to huge investments to their [Huawei Mobile Services](https://www.xda-developers.com/huawei-hms-core-android-alternative-google-play-services-gms/) (counterpart of Google Mobile Services) and even work on greenfield operation system [Harmony OS](https://harmonyosofficial.com/).

## Samsung's Galaxy App Store
Samsung's app store comes preinstalled on its own devices and <a href="bluestacks">Bluestacks</a>. I couldn't find its official installer on their European website, but it's easily downloadable from other app stores - I certainly don't recommend such an approach.

It is quite successful - Google [wants to kill it](https://arstechnica.com/gadgets/2020/07/google-wants-samsung-to-kill-bixby-galaxy-app-store/).

## Amazon AppStore
AppStore comes pre-installed on its Fire devices. They provide rich infrastructure as well.

# Other stores
In many cases, these stores seem to just mirror APKs from Google Play and don't offer any distribution/revenue model directly. I have briefly tried all of these to point out their offering from a developer perspective.

## ApkMirror
Backed by Android Police, [ApkMirror](https://www.apkmirror.com/) provides its own APKMirror Installer. They provide an alternative to app bundle - apkm - as well as traditional APKs.

## ApkPure
[ApkPure](https://apkpure.com/) provides a small console area for app management for developers where you can check stats and comments. They provide their own updater app for users like any other app store also. Their homepage can be installed (PWA) on the home screen - this is neat and simple. Footer on their developer console says they deliver to [10M users worldwide](https://developer.apkpure.com/)

## <h2 id="bluestacks">BlueStacks</h2>
Android Emulator designed to enable Android applications to run on PCs running Microsoft Windows and Apple's macOS. Comes with Samsung Galaxy App preinstalled. They even provide some [enterprise offerings](https://www.bluestacks.com/enterprise.html).

## ApkFab
[ApkFab](https://apkfab.com/) provides common updater app and App Bundle alternative packaging - XAPK (used by ApkPure also).

## GetJar
[GetJar](https://www.getjar.com/) - I have never heard of this one before, seems quite abandoned to me, but used to be quite popular. They distribute apps to over [30 million](https://developer.getjar.mobi/) users a month.

## Aptoide 
[Aptoide](https://en.aptoide.com/) develops a custom [Catappult](https://catappult.io) platform to distribute apps to many stores at once. They push their own cryptocurrency Appcoin. Unfortunately, they are often accused [link 1](https://www.reddit.com/r/Android/comments/f406ne/appcoins_scam_at_aptoide_market/
), [link 2](https://www.reddit.com/r/androiddev/comments/ewijj0/some_store_named_catappult_is_redistributing_my/)) of piracy/redistribution with own ads. They distribute apps to over [300 million](https://en.aptoide.com/company/developers) users.

## Uptodown
[Uptodown](https://en.uptodown.com/android) provides likable interface and also comes with some sort of developer zone. They claim to have [120 million](https://en.uptodown.com/oem) unique users each month, which seems quite impressive. Uptodown was established [in 2003](https://blog.en.uptodown.com/faq-uptodown-common-questions/).

# Open source app clients

## Aurora Store
Open-source client for the Play Store. Tries to provide a complete distribution system, but it is interesting only for FOSS enthusiasts.

## FDroid
F-Droid is an installable catalog of FOSS (Free and Open Source Software) applications for the Android platform. The client makes it easy to browse, install, and keep track of updates.

F-Droid enables one to add its own repository, which can be useful for ditributing private apps inside companies.

# Xiaomi/Oppo/Vivo/Lenovo
These Chinese manufacturers would like to [enter western markets](https://www.cnet.com/news/huawei-xiaomi-vivo-and-oppo-reportedly-to-join-forces-against-google-play-store) with their app stores also, but their app stores are not operable yet.

# <h2 id="emm">Android Enterprise Mobility Management (by Google)</h2>

[Android EMM](https://androidenterprisepartners.withgoogle.com/glossary/emm/) is useful for companies already using G Suite or Cloud Identity.

Private apps are automatically approved when published, but aren't automatically available to a user unless an enterprise IT admin explicitly grants them access to all approved apps. EMM covers management of custom devices (Zebra, Panasonic Toughbook, ...), applications, and management. Android apps are compatible with Android's enterprise features by default. Each G Suite or Cloud Identity account is associated with exactly one [Organization](https://cloud.google.com/resource-manager/docs/creating-managing-organization
). An Organization is associated with exactly one domain, which is set when the Organization resource is created.

EMM is used often with work profiles. Enterprises have control over all data and security policies within the work profile. Outside the work profile, the device remains suitable for personal use—ideal for BYOD deployments.

# Conclusion
Hopefuly I helped you to get orientated in Android app distribution options. I have tried to cover all options I am aware of. If you wish to point out another method you are welcome to discuss below :) .
