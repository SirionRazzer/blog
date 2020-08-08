---
title: Comparison of Android app stores in 2020
date: 2020-07-30 21:18:07
tags: ['android', 'deployment']
thumbnail: /gallery/thumbnails/header.png
categories:
- dev
- android
---
# Welcome to the monopoly
This article aims to answer common questions about possibilities of android app distribution. As of 2020 there exist many app stores and other ways to be chosen from. On the other hand there are not many full fledged solutions available. It is quite easy to distribute an app on its own, yet dealing with further updates or the monetization narrows down these options to only few big houses. Obligatory choice is still Google Play, which provides the most complete services to manage your app's distribution. With some drawbacks there are also Samsung's Galaxy App Store, Huawei's AppGallery, Xiaomi' GetApps and Amazon's AppStore. These come preinstlla	

## FAQ

These questions are often asked by customers. Some of them will be answered further down the article.

### Is it possible to distribute an app outside of any app store?
### How is Android app ditribution different from Apples's AppStore?
### Can an app autoupdate itself?
### Is it possible to distribute an app privately?
### Is it safe to distribute an APK by email?
### Is an APK safe against piracy?
### Is it possible to remotely administrate apps distributed in our company on employees' devices?


# Google Play Store

# Renowned alternatives


Oppo/Vivo/Lenovo
https://www.cnet.com/news/huawei-xiaomi-vivo-and-oppo-reportedly-to-join-forces-against-google-play-store/v 


## Huawei AppGallery
preinstaled on
bundles PWAs??

ze stránek Huawei/Honor stáhnu APK AppGalery, nedostupny z GooglePlay

při instalaci je k běžné výzvě pro instalaci přidružená výzva Google Play Protect (AppGallery využívá vylepšený ochranný proces k ochránění integrity apkčka), instalátor balíčku (nativní, APKMirror Installer, Total Commander...) musí být v dialogu potvrzen, jako důvěryhodný iinstalátor. tato vyzba je tedy asi pouze u prvniho stazeni

po instalaci si vyzada stazeni Huawei Mobile Services (whopping 93 MB) z Google Play

Auto-update over Wi-Fi

Behem updatu AppGallery (sama sebe) ji neni mozne spoustet

Umoznuje ciste instalacni/aktualizacni flow bez potvrzovani aktualizace a instalace balicku, stejne jako Google Play - prestoze neni nainstalovana jako systemova (seamless)

Offers Paid Promotion

## Samsung's Galaxy App Store
preinstaled on Samsung devices and Bluestacks
nedostupny z Google Play


## Amazon AppStore
preinstalled on

# Insignificant alternatives


## ApkMirror
Hostuje APKčka

stoji za nimi Android Police

ML Managerem vytáhnu apk ze systému, uploaduju na apkMirror, tam se ručně reviewuje a nabídne poté ostatním ke stažení... funguje na 6, ale na 9 MIUI i 10.

Z webových stránek stáhnu apk (vyskočí hláška, že může poškodit zařízení)

APKMIrror Installer (Official) dostupný z Google Play Store k instalaci . Instalátor balíčků, obdoba nativního package installeru

apkm (asi obdoba app bundlui).

instalace nativním instalačním dialogem

supports App Bundles (Dynamic Delivery)


## ApkPure
doporucuje Bluestacks

Siganture Verification online tool
Region free APK download tool

XAPK jako u ApkFab

ApkPure - jejich App Store

check installed packages for updates 

Install balicku otevre systemovy install dialog
Update otevre systemovy update dialog
pote nasleduje Google Play Protect hlaska

jejich web se nabizi k instalaci jako PWA na homescreen

poskytuji minimalistickou konzoli k uploadu vlastnich aplikaci, se statistikami a komentari


## BlueStacks
Featured na ApkPure


## ApkFab
APK upload/download hosting, alternative to apkm  od apkmirro je zde xapk

XAPK is a standard zip format which contains Android App Bundles, or installation package (.apk), OBB, cache asserts and other data files to make sure the app download to an Android and run successfully. Google Play Store has a limitation on the app file size, therefore for the app over 100MB, developers can use XAPK file format to allow users download the APK file on Android without corruption. There are two types of .XAPK files right now as below shows.

Google Play hosts the expansion files for your app and serves them to the device at no cost to you. The expansion files can be any format you choose (ZIP, PDF, MP4, etc.) and they usually contain additional resources required by your app.

To make it simple, XAPK = APK + OBB data + Cache + App Icon and Miscellaneous Info.

Maji klasicky APK Downloader, APK Upload a XAPK Manager.


## Aptoide 
stejne jako jine je naplneny skrz katapult https://catappult.io (vyvijeny Aptoidem)
scam, kradou aplikace a cpou do nich vlastni reklamu (Appcoins)
https://www.reddit.com/r/Android/comments/f406ne/appcoins_scam_at_aptoide_market/
catappult je shit scammers
https://www.reddit.com/r/androiddev/comments/ewijj0/some_store_named_catappult_is_redistributing_my/

## TapTap    
east world based targeted store with mainly games

# Open source alternatives


## Aurora Store
open source 
nutno povolit instalovat z tohoto zdroje
nutno klasicky potvrdit instalaci v systémovém dialogu


## FDroid
Nativni install dialog, potom Google Play Protect potvrzeni pri instalaci z tohoto zdroje, pri dalsi instalaci jiz staci pouze odkliknout nativni dialog






## Android Enterprise Mobility Management (by Google)
Glossary https://androidenterprisepartners.withgoogle.com/glossary/emm/


Private apps are automatically approved when published, but aren't automatically available to a user unless an enterprise IT admin explicitly grants them access to all approved apps

Android's enterprise features provide organizations with a secure, flexible, and unified Android mobility platform—combining devices, applications, and management. Android apps are compatible with Android's enterprise features by default.
-- for developerss  Build For Enterprise https://developer.android.com/work/guide
-- private apps how to for developers https://developers.google.com/android/work/play/custom-app-api/publish


https://androidenterprisepartners.withgoogle.com/
Remote device management
https://androidenterprisepartners.withgoogle.com/emm/

Once you have created your G Suite or Cloud Identity account and associated it with a domain, your organization resource will be automatically created for you. The resource will be provisioned at different times depending on your account status:

Each G Suite or Cloud Identity account is associated with exactly one Organization. An Organization is associated with exactly one domain, which is set when the Organization resource is created.
https://cloud.google.com/resource-manager/docs/creating-managing-organization


-- managed Google Play Account
https://support.google.com/googleplay/work/answer/6137769?hl=en

Devices
-- Zebra, Panasonic Toughbook

Work profiles
-- Enables platform-level separation of work apps and data. Enterprises have control over all data and security policies within the work profile. Outside the work profile, the device remains suitable for personal use—ideal for BYOD deployments.
Work app management
-- Benefit from Android's full suite of enterprise app management capabilities, including silent app distribution, private app support, and more.


## Epic https://www.epicgames.com/fortnite/en-US/mobile/android/get-started
https://techcrunch.com/2018/09/07/fortnite-hits-15-million-installs-on-android/?guccounter=1&guce_referrer=aHR0cHM6Ly9uZXdzLnljb21iaW5hdG9yLmNvbS8&guce_referrer_sig=AQAAACRvmvDp_QEkxeLSrF_Mgxnf-z6x4Qd53T5QPQDcgS4EhL7pspZ3fL5epJNN-IcygCfwDExuEQPXoRp3LzJyLONbM5dQmDGHZwALkIeWCjrP6qi4AbOdVk6Bv0bfQ9gfNdMN0pHhSJs1BjTLYE5P5oPYFoKYRDNS8UT-adGw0mDM
* Fortnite revenue
## Email

# Market share

## HMS vs GMS
HMS dostupne z GooglePlay

## Comparison
- Quick Apps (huawei AppGallery)
- Instant Apps (google play)

## Cover your enterprise needs

## Conclusion
* Keep ALL doors open
