---
title: 'Android: Release shamelessly, outrun a hacker'
date: 2020-05-18 23:24:09
tags: ['android', 'pentesting']
categories:
- dev
- android
---
# Keep an eye on attack vectors with MobSF
Your shiny new Android app is almost done and you are heading for release. Your most valuable assets are baked inside your app, yet there is one last crucial measurement your app should undertake to ensure its security.

The plethora of insecure practices developers were not aware of during the development process as well as hidden weaknesses inside third-party dependencies may create a serious security hole inside the final product. Once you publish your app anyone can reverse engineer it and extract any secrets. This can lead to security breach on the backend side or data leak from app’s storage. Moreover any app can be repackaged with attacker’s malicious code and released on Google Play to lure your customers away.

As of 2020 there are many analysis tools available for Android app inspection. The one I can highly recommend is Mobile Security Framework [MobSF](https://github.com/MobSF/Mobile-Security-Framework-MobSF) suggested by [OWASP](https://owasp.org/www-pdf-archive/OWASP-Tales-of-practical-penetration-testing.pdf) both for static and dynamic analysis. With over 6000 stars it is one of the most popular repository amongst security frameworks for mobile devices. DevSecOps teams can incorporate it into their CI/CD pipelines. It is hosted locally, which means sensitive data never interacts with the cloud.

You definitely don’t need to have a deep knowledge of Android security to perform your first inspection with MobSF.

1. Install MobSF with [setup script](https://mobsf.github.io/docs/#/installation)
``` bash
$ git clone https://github.com/MobSF/Mobile-Security-Framework-MobSF.git
$ cd Mobile-Security-Framework-MobSF
$ ./setup.sh
```
2. Open Dashboard at localhost:8000 and upload your apk file
{% asset_img MobSF_upload.png Upload apk file %}

3. Wait till the scanning finishes and evaluate report
{% asset_img MobSF_dashboard.png This is an example image %}

Being a developer you should focus on these parts:
- Security Score
- Exported Activities, Services, Receivers and Providers
- Certificate Status
- Application Permissions - the less you need the better
- Manifest Analysis - check the severity of issues
- Code Analysis - insecure access, temporary files created, SQL injection warning, hardcoded strings (keys, emails, passwords), sensitive information logging, exposed URLs

From the business standpoint of view this report may present a worthy bonus for your customer. Thanks to this report both you and your customer will secure their interests and most importantly, release shamelessly!
