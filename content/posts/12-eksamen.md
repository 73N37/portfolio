---
title: "12-Demo-Eksamensforberedelse: Demonstration af Projekter og Opsamling"
date: "2026-05-29"
description: "Den store finale: Demonstration af vores færdige Gods-bookingassistent, feedback fra undervisere, samt opsamling og forberedelse til den mundtlige eksamen."
showTableOfContents: true
showHero: true
draft: false
tags:
  - "AIDA"
  - "Projektdemo"
  - "Eksamen"
  - "Opsamling"
  - "Refleksion"
categories:
  - "Undervisning"
---

Velkommen til den tolvte og allersidste logbog på mit portfolio-website for **AIDA Spring 2026**!

Dette var vores **store finale-dag**. Efter ugers intensiv læring, design og kodning mødtes hele klassen til **projektdemonstrationer**. Alle teams viste deres færdige løsninger frem og modtog feedback fra undervisere og medstuderende. Derefter samlede vi op på hele valgfagets faglige rejse og kiggede frem mod den kommende mundtlige eksamen.

---

## Praktisk info om sessionen

* **Undervisningsgang:** 12 (Dato: 29/5)
* **Tema:** Projektdemo + eksamensforberedelse
* **Dagens Mål:** Demonstrere vores færdige Gods-bookingassistent for klassen, modtage feedback, foretage en samlet refleksion over valgfaget, samt strukturere forberedelsen til den mundtlige eksamen.

---

## Hvad vi gjorde i undervisningen

Dagen var opdelt i to store spor:

### 1. Projektdemo-runden
Alle grupper kørte en live demonstration af deres AI-drevne applikationer. Det var fantastisk at se den store diversitet i løsningerne, som spændte over alt fra fuldautomatiske e-mail agenter, intelligente PDF-analysatorer, til avancerede RAG-løsninger.

Vores gruppe præsenterede **Booking- og Info-assistenten til Engestofte Gods**. Vi kørte en live demo, hvor vi:
* Modtog en fiktiv kundemail med en lang række komplicerede spørgsmål om bryllupspriser, overnatningskapacitet og specifikke menuer.
* Viste hvordan Express-backenden flettede mailen sammen med vores Dify RAG-kilde og genererede et fejlfrit, høfligt og præcist svarudkast på under 10 sekunder.
* Demonstrerede vores administrations-brugergrænseflade, hvor Lise eller Mette-Marie nemt kunne rette i teksten, inden mailen blev godkendt og sendt afsted.

Løsningen modtog stor ros for sin **stabilitet, klare forretningsværdi og gennemtænkte sikkerhed** (særligt i forhold til credential-håndtering og *human-in-the-loop* tilgangen).

### 2. Eksamensforberedelse & Opsamling
Efter demoerne samlede Jon og Jesper op på valgfagets samlede forløb. Vi kiggede tilbage på vores rejse fra de spæde trin med Hugo og simple embeddings til komplekse API-integrationer, spec-driven development og Model Context Protocol. Vi sluttede af med en session om den mundtlige eksamensform og fik præsenteret en række gode råd til forberedelsen.

---

## Refleksionsartikel: En samlet evaluering af min læringsrejse i AIDA

Nu hvor undervisningen er overstået, og vores portfolio er komplet, er det tid til at gøre status over min personlige læring på AIDA Spring 2026.

### De tre vigtigste ting, jeg tager med mig
1. **RAG er let at bygge, men svært at mestre:** At uploade et dokument i en no-code chatbot tager få minutter, men at sikre høj præcision (retrieval precision) og deterministiske svar (Structured Outputs) kræver dyb forståelse for datastrukturering, kilde-parsing og systematisk evaluering.
2. **AI-agenter kræver stærke specifikationer:** Vores kodningsagenter er kun så gode som vores specifikationer. Spec Driven Development er ikke blot en smart AI-trend, men en nødvendig metodik for at bevare kontrollen over systemarkitekturen og undgå teknisk gæld.
3. **Sikkerhed er ikke valgfrit:** API-nøgler skal beskyttes med samme stringens som produktions-passwords. proxy-arkitekturer og streng brug af miljøvariabler skal være en rygradsreaktion hos enhver moderne softwareudvikler.

### Min plan for den mundtlige eksamen
Til den mundtlige eksamen vil jeg tage udgangspunkt i vores Gods-projekt og bruge det som en case til at demonstrere min forståelse for:
* **Brobygningen** mellem det deterministiske (traditionel kildekode) og det probabilistiske (sprogmodeller).
* **Teoribygningen** (Peter Naur), og hvordan vi har brugt specifikationer og test til at styre vores kodningsagenter sikkert.
* **Fremtidsperspektivet** i Model Context Protocol (MCP), og hvordan det kan transformere systemer fra statiske API-kald til dynamiske, agentiske workflows.

---

## Værktøjer og ressourcer anvendt

* **[Forslag til den mundtlige eksamen](./mundtlig-eksamen)** - Dagens guide til eksamensforberedelse.
* **Blowfish / Hugo Portfolio** - Færdiggørelse og finpudsning af dette portfolio-website.

---

*Hermed lukkes logbogen for AIDA Spring 2026. Det har været en sand fest!*
