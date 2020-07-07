---
title: "Scoreboard SPA built on the cheap using mainly nocode techniques in 2 hours"
date: 2020-07-07 23:24:09
tags: ["jamstack", "nocode", "SPA", "JS"]
categories:
  - dev
  - SPA
---

This is not a tutorial, but a quick write-up about the simplicity of tools which can be used to publish simple single page application nowadays. I have used this approach a few times when someone asked me to build an editable table of items (ie. upcoming events) without special requirements. I wouldn't recommend this approach for anything more serious.

## Tooling

- [html5up](https://html5up.net/) as a responsive HTML template
- [Google Sheets](https://www.google.com/sheets/about/) as an editable database
- [SheetDB](https://sheetdb.io/) to convet Google Sheets into simple api
- [ApexCharts chart template](https://apexcharts.com) to display scores nicely
- my 3\$ Ubuntu VPS with Apache and Let's Encrypt to deploy the result

## Motivation

I was in need of simple editable scoreboard for children summer camp. Scores should be updated independently by a few animators and displayed on the temporary page published during the event.

## API + Database

Google Sheets is an excellent choice due to three reasons. Firstly, everyone can access and edit shared sheet using browser or mobile app. Secondly, there are SaaS platforms like SheetDB which can turn sheet into consumable API. And finally, I could leverage the simplicity provided by both of these to speed up the most cumbersome part of this project.

Sheets-into-API approach is quite popular today, there are many competitors in this field like [SheetDB](https://sheetdb.io/), [Sheetsu](https://sheetsu.com/), [Sheet.Best](https://sheet.best/) and many more. I wish Google itself made such a simple API to its Sheets, but I guess Google is just more focused on its Firebase cloud business.

### Google Sheets

{% asset_img spreadsheet.png Google Sheets %}

### SheetDB

{% asset_img sheetdb.png SheetDP API %}

## Frontend

The place I visit every time when I need a responsive static site is [html5up](https://html5up.net/). Their templates come with example page populated with all design options and further customization is possible with the provided Sass file. When doing small project like this one, these templates can help me kickoff the frontend in a minute without sacrificing of the responsiveness and with decent eye-candy.

{% asset_img html5up.png 'Directive' template by html5up %}

## Displaying data

I wanted to display the scoreboard with plain horizontal chart, the chosen one from [ApexCharts](https://apexcharts.com)'s works as expected.

The data are fetched from the API with simple `fetch` and then sorted by the score value.

```JS
    fetch("https://sheetdb.io/api/v1/[real token removed]")
        .then(res => {
            res.json().then(res => {
                // skipped data tranformation...
                var chart = new ApexCharts(document.querySelector("#chart"), options);
                chart.render();
    ...

```

## Hosting

For hosting of small projects I prefer the VPS and leverage Apache's capability to host multiple sites (VirtualHosts). My usual routine is to create appropriate folder inside `/var/www/[DOMAIN-NAME.NAME]`, then create site's configuration file with `<VirtualHost *:80>` directive in `/etc/apache2/site-available/[HERE].conf`, enable it with `a2ensite *` command and issue SSL certificate with Let's Encrypt's Certbot client. Certbot creates copy of configuration file with certificate paths populated appropriately and I can finally upload frontend files and fill a glass of wine.

## Result & evaluation

The resulting SPA was created in much shorter time than this post. Except for the JS fetch part of data into chart there were zero lines of code written elsewhere. I can recommend this approach only for the project with constraint funding and one-shot temporary applications as stated in the preface.

{% asset_img result.png Finished SPA with placeholder data %}