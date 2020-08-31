---
title: Hello Kotlin Backend
date: 2020-08-28 22:03:25
tags: ['kotlin', 'backend', 'spring boot', 'strapi']
thumbnail: /gallery/thumbnails/header5.png
toc: true
categories:
- dev
- backend
---

I have joined a new project which is already bootstrapped with Spring Boot and Kotlin. I haven't needed such tech stack yet, usual requirements were easily solvable by deploying the Strapi CMS and the database.

<!-- more -->

I was initially pleasingly surprised that Spring Boot can be used with Gradle and Kotlin. This made me feel more confident with my first steps since I knew both of these already from Android development.

The Strapi comes with authorization and access control out of the box. This eases the complexity of API development. On the other hand, this is a quite opinionated approach and goes against the architecture decoupling. Spring Boot is designed as microservice, self-contained and concise framework and authorization and access control are not available directly.

I guess I will start with Spring Security since there is a nice article by [Baeldung](https://www.baeldung.com/spring-security-basic-authentication). Another option would be [Keycloak](https://www.keycloak.org/) identity & access management server, but I lack the skills needed to deploy it reliably and I think it is a bit overkill for the current project. Maybe later.