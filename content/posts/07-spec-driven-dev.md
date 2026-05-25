---
title: "07-Spec-Driven-Dev: AI-Metoder, Jura og Peter Naurs Teoribygning"
date: "2026-05-01"
description: "Refleksioner over Spec Driven Development til kodeagenter, etiske/juridiske aspekter ved AI samt Peter Naurs klassiske programmeringsteori."
showTableOfContents: true
showHero: true
draft: false
tags:
  - "AIDA"
  - "Spec-Driven-Dev"
  - "Peter Naur"
  - "Etik"
  - "Jura"
  - "Refleksion"
categories:
  - "Undervisning"
---

Velkommen til den syvende logbog på mit portfolio-website for **AIDA**!

Dagens modul markerede en vigtig kobling mellem **systemudviklingsmetodik, etik/jura** og computerpioneren **Peter Naurs banebrydende tanker**. Vi diskuterede, hvordan vi som softwareudviklere arbejder systematisk og sikkert i en tidsalder, hvor kodningsagenter udfører det manuelle arbejde, og hvordan vi strukturerer vores krav for at undgå agent-faldgruber.

---

## Praktisk info om sessionen

* **Undervisningsgang:** 7 (Dato: 1/5)
* **Tema:** Spec Driven Development & Juridiske/etiske overvejelser
* **Dagens Mål:** Forstå Spec Driven Development (SDD) som styrende metode for agenter. Diskutere juridiske og etiske aspekter (GDPR, bias). Reflektere over Peter Naurs artikel "Programming as Theory Building".

---

## Hvad vi gjorde i undervisningen

Vi gennemgik tre tæt forbundne emner:

### 1. Spec Driven Development (SDD)
Når vi bruger AI-agenter (som Claude Code eller GitHub Copilot Workspace), dur traditionel ad-hoc programmering ikke. Hvis vi giver en agent en løs instruktion, bygger den ofte noget uforudsigeligt eller uhensigtsmæssigt. 

I SDD skriver vi en **formel, præcis specifikation** *inden* koden skrives. Denne specifikation indeholder:
* **Mål:** Hvad skal systemet kunne?
* **Teknisk stak:** Hvilke frameworks, biblioteker og databaser skal anvendes?
* **Flows:** Hvordan flyder data gennem systemet?
* **Acceptkriterier:** Præcise tests eller scenarier, der skal være opfyldt.

Agenten læser specifikationen og genererer kode, der matcher den 100%. Vi som udviklere agerer revisorer og sikrer, at specifikationen er korrekt, og at det genererede produkt opfylder kravene.

### 2. Juridiske og etiske aspekter af AI
Vi diskuterede de alvorlige problemstillinger ved at integrere eksterne LLM'er i kommerciel software:
* **GDPR og datasikkerhed:** Vi må aldrig sende personfølsomme oplysninger (PII) til eksterne API'er uden samtykke eller en databehandleraftale (DPA). Data anvendes ofte til træning, medmindre man eksplicit fravælger det via API-indstillinger.
* **EU's AI Act (dataforordningen):** Vi så på de kommende juridiske krav i EU, der klassificerer AI-systemer efter risikoniveau.
* **Bias og diskrimination:** LLM'er er trænet på internettet og bærer menneskelige fordomme. Hvis vi bygger en vurderingsapplikation eller et rekrutteringsværktøj, skal vi sikre, at systemet ikke diskriminerer baseret på køn, etnicitet eller baggrund.

### 3. Peter Naur: Programming as Theory Building
Vi læste computerpioneren Peter Naurs klassiske artikel fra 1985. Naurs hovedtanke er, at **programmering ikke blot handler om at producere programtekst, men om at opbygge en teori (forståelse) i udviklerens hoved** af, hvordan systemet og virkeligheden hænger sammen. 

Naur argumenterer for, at hvis de oprindelige udviklere forlader et projekt, dør "teorien", og nye udviklere vil have utrolig svært ved at vedligeholde systemet – selvom der findes omfattende dokumentation.

---

## Refleksionsartikel: Specifikationer og Teoribygning i en AI-tidsalder

Kombinationen af Spec Driven Development og Peter Naurs teorier giver et utrolig spændende perspektiv på vores fremtidige faglighed.

### Specifikationer som agenthviskeren
I en tidsalder, hvor koden skrives af AI, bliver **specifikationen vores primære kildekode**. Den udvikler, der kan skrive den mest præcise, arkitektonisk gennemtænkte specifikation, vinder. 

Uden klare specs fanges vi i "spec-fælden", hvor agenten bygger ustruktureret kode, som vi efterfølgende bruger timer på at rette. Mit mål fremover er altid at udarbejde en formel specifikationsfil (`spec.md` eller lignende) i roden af mine projekter, før jeg lader en kodeagent skrive en eneste linje kode.

### Peter Naur vs. AI Agenter
Hvis programmering er "teoribygning" i udviklerens hoved, hvad sker der så, når vi uddelegerer kodningen til en AI? 
* **Risikoen:** Vi risikerer at miste vores egen "teori" om systemet. Hvis vi blot godkender AI'ens kode uden at forstå den, besidder vi ikke længere teorien bag programmet. Vi bliver fremmede i vores eget codebase.
* **Løsningen:** Vi skal bruge AI-agenterne til at accelerere skrivningen, men vi skal *selv* styre teoribygningen. Vi skal designe systemet arkitektonisk og bruge agenterne som flittige håndværkere, der udfører vores vision under strengt opsyn. Specifikationer er netop redskabet, der tvinger os til at formulere og fastholde vores egen teori om programmet.

---

## Værktøjer og ressourcer anvendt

* **[Peter Naur - Programming as Theory Building](/toolbox/llm-integration/tjekliste)** - Den klassiske artikel i markdown-format.
* **[Fra Martin Fowlers Blog om SDD](https://martinfowler.com/articles/exploring-gen-ai/sdd-3-tools.html)** - Udforskning af Spec-Driven Development og AI.
* **[The AI Dilemma (Video)](https://www.youtube.com/watch?v=xoVJKj8lcNQ)** - Dybdegående video om de etiske udfordringer ved moderne AI-teknologi.

---

*Logbog afleveret som en del af eksamensforberedelsen.*
