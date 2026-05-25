---
title: "10-Sparring: Projektudvikling og Sikker Håndtering af API-nøgler"
date: "2026-05-18"
description: "Erfaringer fra projektarbejdet, sparring på systemarkitektur samt en dybdegående gennemgang af sikker håndtering af API-nøgler under udviklingen."
showTableOfContents: true
showHero: true
draft: false
tags:
  - "AIDA"
  - "Projektarbejde"
  - "API-Keys"
  - "Sikkerhed"
  - "Blowfish"
  - "Refleksion"
categories:
  - "Undervisning"
---

Velkommen til den tiende logbog på mit portfolio-website for **AIDA**!

Dagens session var præget af intensivt projektarbejde i grupperne, krydset med teknisk sparring fra vores undervisere. Derudover havde vi et kritisk og yderst aktuelt oplæg om **sikkerhed og håndtering af API-nøgler og credentials** under titlen *"Is it secret? Is it safe?"*. Dette er et afgørende emne, når vi bygger applikationer, der trækker på betalte AI-tjenester.

---

## Praktisk info om sessionen

* **Undervisningsgang:** 10 (Dato: 18/5)
* **Tema:** Projektarbejde + håndtering af nøgler
* **Dagens Mål:** Få sparring på vores igangværende arkitektur, og lære bedstepraksis for at beskytte vores API-nøgler mod misbrug og utilsigtet eksponering på GitHub.

---

## Hvad vi gjorde i undervisningen

Dagen startede med et super skarpt oplæg om sikkerhed. Når vi bygger traditionelle applikationer, er en lækket API-nøgle til et gratis API måske ikke katastrofalt. Men når vi arbejder med sprogmodel-API'er (som OpenAI eller Google Gemini), kan en lækket nøgle blive en **dyr fornøjelse**. Botter scanner konstant GitHub efter eksponerede nøgler, og inden for få minutter kan en lækket nøgle blive misbrugt for tusindvis af dollars.

Vi gennemgik de vigtigste sikkerhedsregler:
* **Brug ALDRIG rå API-nøgler i kildekoden:** Nøgler skal holdes fuldstændig adskilt fra logikken.
* **Miljøvariabler (`.env`):** Anvendelse af `.env` filer til at opbevare følsomme variabler lokalt, kombineret med en streng `.gitignore` fil, der forhindrer, at `.env` nogensinde pushes til GitHub.
* **Backend-proxies:** Hvis vi har en frontend (fx React eller statisk HTML), må vi *aldrig* foretage direkte API-kald til OpenAI derfra, da brugerne blot kan inspicere netværkskaldene i browseren og stjæle nøglen. Alle kald skal routes gennem vores egen backend (proxy), som opbevarer nøglen sikkert på server-niveau.

Derefter arbejdede vi videre i vores projektgrupper, hvor vi fik værdifuld sparring på vores database-design og integrationen mellem vores Express-backend og Dify API'et.

---

## Refleksionsartikel: "Is it secret? Is it safe?" – En personlig lærestreg

Oplægget om sikkerhed ramte hovedet på sømmet, da vi i vores gruppe faktisk havde en sund diskussion om, hvordan vi bedst strukturerede vores credentials.

### Sikkerhed som en fundamental del af arkitekturen
Det er en klassisk faldgrube for studerende at tænke: *"Vi koder bare løsningen først med nøglen hårdtkodet, og så rydder vi op i det inden aflevering"*. 

Men sikkerhed er ikke noget, man kan "klistre på" til sidst. Det skal tænkes ind fra dag ét. Hvis en nøgle først er blevet pushet til GitHub i en historisk commit, er den kompromitteret – selvom du sletter den i den nyeste commit. Git husker alt. Hvis man begår denne fejl, skal man straks trække nøglen tilbage (revoke) hos udbyderen og generere en ny.

### Vores Sikkerhedsarbejdsgang
I vores Gods-projekt implementerede vi straks følgende struktur:
1. **`.env.template`:** Vi oprettede en skabelonfil i vores Git-repository uden faktiske nøgler (fx `OPENAI_API_KEY=your_key_here`). Dette viser andre udviklere på holdet, hvilke variabler de skal konfigurere lokalt.
2. **Backend Gateway:** Vi sikrede, at vores frontend kun taler med Express-serveren, som derefter varetager den sikre kommunikation med Dify. Dette beskytter mod, at vores API-nøgler eksponeres i browseren.

### Konklusion
At bygge AI-drevne applikationer kræver en moden tilgang til sikkerhed. Oplægget gav os en sund respekt for de økonomiske og sikkerhedsmæssige risici, der er forbundet med moderne API'er. Med vores nye struktur på plads føler vi os fuldstændig trygge ved at fortsætte projektarbejdet og udvide vores backend med avancerede funktioner.

---

## Værktøjer og ressourcer anvendt

* **[Is it secret? Is it safe? (Slides)](is-it-secret-is-it-safe.pdf)** - Dagens slides om API-nøglesikkerhed.
* **dotenv** - Node.js bibliotek til indlæsning af miljøvariabler.
* **`.gitignore`** - Konfigureret til strengt at udelukke `.env` og lokale konfigurationsfiler.

---

*Logbog afleveret som en del af eksamensforberedelsen.*
