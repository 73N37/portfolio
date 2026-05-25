---
title: "04-Kodeagenter: AI som Aktiv Samarbejdspartner i Softwareudvikling"
date: "2026-04-20"
description: "Erfaringer med brug af avancerede kodeagenter som Claude Code og terminal-baserede AI-værktøjer til systemarkitektur, debugging og refactoring."
showTableOfContents: true
showHero: true
draft: false
tags:
  - "AIDA"
  - "Kodeagenter"
  - "Claude Code"
  - "Softwareudvikling"
  - "Refactoring"
  - "Refleksion"
categories:
  - "Undervisning"
---

Velkommen til den fjerde logbog på mit portfolio-website for **AIDA**!

Dagens modul handlede om et af de mest spændende og hurtigst voksende områder inden for AI-drevet softwareudvikling: **AI-baserede kodeagenter**. Vi bevægede os væk fra simple chat-grænseflader og kiggede på, hvordan agenter (såsom Claude Code og Gemini-baserede CLI-agenter) aktivt kan integreres i vores daglige udviklingsmiljø til at løse komplekse, fler-trins opgaver.

---

## Praktisk info om sessionen

* **Undervisningsgang:** 4 (Dato: 20/4)
* **Tema:** Kodeagenter i softwareudvikling
* **Dagens Mål:** Forstå forskellen på simple AI-chatbots og agentiske systemer. Lære at bruge en kodeagent til arkitektur, debugging, refactoring og testskrivning, samt dokumentere workflowet.

---

## Hvad vi gjorde i undervisningen

Vi startede med en teoretisk gennemgang af evolutionen inden for AI-kodningsværktøjer:
1. **Første generation:** Simple chatbots (ChatGPT i browseren), hvor man manuelt skal kopiere kode frem og tilbage.
2. **Anden generation:** Inline-kodningsassistenter (GitHub Copilot i VS Code), der foreslår linjer eller funktioner baseret på kontekst.
3. **Tredje generation (Agenter):** Værktøjer der opererer direkte i vores terminal og filsystem (såsom Claude Code). En agent kan læse hele codebase-strukturer, køre test-kommandoer, analysere kompileringsfejl og selvstændigt rette filer i flere iterative trin.

### Dagens praktiske øvelse
Vi fik til opgave at løse en konkret programmeringsopgave udelukkende ved hjælp af en kodeagent. Workflowet var som følger:
* Vi definerede opgaven og acceptkriterierne for agenten.
* Agenten scannede projektmappen, analyserede de eksisterende filer og kom med et løsningsforslag.
* Vi gav agenten tilladelse til at skrive og modificere koden i projektet.
* Vi kørte tests (både manuelt og via agenten) og lod agenten rette de fejl og edge-cases, som opstod undervejs.

---

## Refleksionsartikel: Fra 'Koder' til 'Dirigent' – Udviklerens nye rolle

Arbejdet med kodeagenter giver et klart smugkig ind i fremtidens softwareudvikling, og det tvinger os til at genoverveje vores egen faglighed som udviklere.

### Fordele ved agentiske workflows
* **Ekstrem hastighed på kedelige opgaver:** Agenten kan lynhurtigt generere omfattende test-suiter, refaktorere boilerplate-kode og opsætte standard integrationer. Det, der før tog timer, tager nu minutter.
* **Fremragende debugging-partner:** Når man står over for en kryptisk fejlmeddelelse, kan agenten lynhurtigt søge på tværs af hele kildekoden, finde den skyldige linje og foreslå en præcis rettelse.
* **Reducering af kontekstskift:** Fordi agenten arbejder direkte i terminalen eller editoren, slipper man for at skifte til browseren, søge på Stack Overflow eller dokumentationssider.

### Udfordringer og faldgruber
* **Tab af arkitektonisk kontrol:** Hvis man blot lader agenten kode derudaf uden opsyn, risikerer man at ende med en "spaghettikode-arkitektur". Agenten optimerer ofte for at løse den specifikke opgave *lige nu*, uden blik for langsigtede designmønstre eller systemets samlede renhed.
* **Faren ved "blind tillid":** Det er ekstremt vigtigt, at man som udvikler forstår alt, hvad agenten ændrer. Vi skal agere som kritiske revisorer. Hvis vi ikke læser koden igennem og forstår logikken, mister vi evnen til at vedligeholde systemet i fremtiden.
* **"Code Bloat":** Fordi det er gratis og hurtigt at generere kode, er der en tendens til, at systemer vokser unødigt meget. Mindre, velovervejet kode er næsten altid bedre end massive mængder AI-genereret kode.

### Konklusion
Min konklusion efter at have arbejdet hands-on med en kodeagent er, at vores rolle som softwareudviklere er under hastig forandring. Vi går fra at være dem, der skriver koden linje for linje (the typewriter), til at være arkitekter og dirigenter (the orchestrator). 

Det stiller langt større krav til vores evner inden for **systemarkitektur, kritisk kodegennemgang (code review), specifikationer og test** fremover. AI-agenten er en fantastisk assistent, men det er stadig mennesket, der skal besidde den dybe systemforståelse for at sikre kvalitet og sikkerhed.

---

## Værktøjer og ressourcer anvendt

* **[Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code)** - Terminal-baseret AI-kodningsagent fra Anthropic.
* **Gemini CLI** - CLI-baseret integrationsværktøj.
* **Local Test Suite** - Kørsel og validering af agentens rettelser.

---

*Logbog afleveret som en del af eksamensforberedelsen.*
