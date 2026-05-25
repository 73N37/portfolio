---
title: "09-Projektstart: Teamdannelse, Case-valg og Systemskitse"
date: "2026-05-11"
description: "Officiel projektstart for eksamensprojektet. Dannelse af projektteams, afgrænsning af casen samt udarbejdelse af projektbeskrivelse og systemskitse."
showTableOfContents: true
showHero: true
draft: false
tags:
  - "AIDA"
  - "Projektstart"
  - "Systemarkitektur"
  - "Express"
  - "NodeJS"
  - "Refleksion"
categories:
  - "Undervisning"
---

Velkommen til den niende logbog på mit portfolio-website for **AIDA**!

Efter virksomhedsoplægget fra Engestofte Gods i sidste modul, var det i dag tid til den **officielle projektstart**. Vi dannede vores endelige grupper, valgte vores case, og lagde de allerførste sten til systemets arkitektur ved at udarbejde en formel projektbeskrivelse og en detaljeret systemskitse.

---

## Praktisk info om sessionen

* **Undervisningsgang:** 9 (Dato: 11/5)
* **Tema:** Projektstart
* **Dagens Mål:** Få dannet det endelige projektteam, låse sig fast på en case, formulere projektets omfang (scope) og tegne en systemskitse over dataflowet.

---

## Hvad vi gjorde i undervisningen

Dagen var præget af intens gruppearbejde og indledende arkitektur-diskussioner. 

### 1. Valg af Case: Booking- og Info-assistenten til Engestofte Gods
Vores gruppe valgte at arbejde videre med godsets udfordringer vedrørende den store mængde repetitive forespørgsler fra gæster. Vi besluttede at bygge en **intelligent, kontekstbevidst mail- og infoassistent**, der kan reducere administrationstiden markant for godsets personale.

### 2. Udarbejdelse af Systemskitsen
For at sikre, at vi bygger et robust system, brugte vi meget tid på at tegne og afstemme systemskitsen. Vi ønskede ikke bare en "dum" wrapper omkring ChatGPT, men et rigtigt tre-lags system.

Arkitekturen indeholder følgende komponenter:
* **Frontend:** En ren og indbydende administrations-brugergrænseflade, hvor personalet kan se indkomne forespørgsler, få præsenteret AI'ens genererede svarkladder, redigere i dem og sende dem afsted.
* **Backend (Node.js/Express eller Python):** Håndterer asynkron logik, API-endpoints, validering og kommunikation med sprogmodeller og databaser.
* **RAG & Vektor-database (Dify eller Pinecone):** Her ligger godsets vidensbase (priser, ledige datoer, bryllupsbetingelser, menuer) opdelt i strukturerede markdown-chunks.

---

## Refleksionsartikel: Arkitektoniske overvejelser og vigtigheden af scope

Det er utrolig let at over-scopet sit projekt ved start. Man vil gerne bygge alt: automatisk e-mail synkronisering, kalenderintegrationer, betalingsgateways og avancerede AI-agenter. Men vi lærte hurtigt, at en **simpel og robust kerne** er langt bedre end et komplekst, ustabilt system.

### Vigtigheden af det begrænsede 'Scope'
Vores vigtigste arkitektoniske beslutning var at holde systemet **semi-automatisk**. Vi fravalgte at lade AI'en sende mails direkte til kunderne. Selvom teknologien tillader det, er risikoen for, at AI'en lover en gæst en forkert pris eller en optaget dato, simpelthen for stor for en eksklusiv forretning. 

Ved at placere en medarbejder i midten (human-in-the-loop) beskytter vi godsets brand, samtidig med at vi stadig sparer dem for 80-90% af skrivearbejdet.

### Valg af Teknologier
Vi besluttede at bygge backenden i **Node.js med Express**, da det er en stak, vi kender godt, og som har fremragende understøttelse af asynkrone API-kald. Til vidensbasen anvender vi Dify's API, da Dify leverer en fantastisk out-of-the-box chunking- og retrieval-motor. Dette sparer os for at skulle programmere vores egne embeddings- og vektor-søgninger helt fra bunden, så vi kan fokusere på forretningslogikken og den gode brugeroplevelse.

---

## Næste skridt

* Opsætning af Git-repository og det grundlæggende projektmiljø.
* Implementering af den basale backend med endpoints.
* Forberedelse af testsæt til at afprøve retrieval-kvaliteten på godsets rigtige bryllupsmaterialer.

---

*Logbog afleveret som en del af eksamensforberedelsen.*
