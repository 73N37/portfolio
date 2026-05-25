---
title: "11-MCP: Kundemøde over Teams, Model Context Protocol og Eksamenstjek"
date: "2026-05-22"
description: "Erfaringer fra onlinemødet med Mette-Marie og Lise, introduktion til Model Context Protocol (MCP) samt de endelige krav til eksamensafleveringen."
showTableOfContents: true
showHero: true
draft: false
tags:
  - "AIDA"
  - "MCP"
  - "Kundemøde"
  - "Engestofte Gods"
  - "Eksamen"
  - "Refleksion"
categories:
  - "Undervisning"
---

Velkommen til den ellevte logbog på mit portfolio-website for **AIDA**!

Dette var vores næstsidste undervisningsgang før den endelige demo-dag, og den var spækket med spændende indslag. Vi startede med et **onlinemøde over Teams med vores kunder fra Engestofte Gods**, fulgte op med en yderst spændende miniworkshop om **Model Context Protocol (MCP)**, og afsluttede med en vigtig briefing om de formelle krav til vores forestående eksamensaflevering.

---

## Praktisk info om sessionen

* **Undervisningsgang:** 11 (Dato: 22/5)
* **Tema:** Kundemøde, MCP og eksamensbrief
* **Dagens Mål:** Afholde opfølgende kundemøde med godset, forstå værdien af Model Context Protocol (MCP), samt få 100% styr på kravene til Wiseflow-afleveringen.

---

## Hvad vi gjorde i undervisningen

Dagens program var opdelt i tre skarpe moduler:

### 1. Onlinemøde med Engestofte Gods
Da det er pinsesæson, har Mette-Marie og Lise ekstremt travlt på godset med afholdelse af store events. Derfor mødtes vi online over **Teams** kl. 9.30 for at præsentere vores foreløbige systemarkitektur og svarkladder. 

Mødet var en stor succes:
* De var begejstrede for vores *human-in-the-loop* tilgang, hvor de bevarer fuld kontrol over svarkladderne.
* Vi fik afklaret en række vigtige edge-cases vedrørende prissætning af bryllupspakker og bookingbetingelser.
* De lovede at eftersende yderligere FAQ-materialer og kontraktskabeloner om mandagen, så vi kan gøre vores RAG-vidensbase endnu mere komplet.

### 2. Miniworkshop: Model Context Protocol (MCP)
Efter mødet dykkede vi ned i et spritnyt og revolutionerende koncept: **Model Context Protocol (MCP)**. 

MCP er en åben standard udviklet af Anthropic, som gør det muligt for sprogmodeller (lokale agenter) at kommunikere med eksterne datakilder og værktøjer på en sikker og standardiseret måde. I stedet for at vi skal skrive specialdesignede integrationer for hver eneste database eller API, kan vi konfigurere en **MCP-server**, som sprogmodellen direkte kan forespørge. Dette åbner op for, at AI-agenter kan læse og skrive i vores lokale databaser, tilgå dokumenter, køre terminalværktøjer og meget mere via en fælles protokol.

### 3. Eksamenstjekliste og Wiseflow-krav
Vi afsluttede dagen med at gennemgå de formelle krav til eksamensafleveringen:
* **Afleveringsfrist:** Senest d. **26. maj 2026 kl. 12:00** på Wiseflow.
* **Format:** Vi skal gemme linket til vores færdige portfolio-website i en markdown-fil navngivet `portfolio.md` og uploade den som vores primære aflevering.

---

## Refleksionsartikel: MCP som fremtidens brobygger for intelligente agenter

Miniworkshoppen om MCP var uden tvivl en af kursets største teknologiske øjenåbnere. 

### Hvorfor MCP er et paradigmeskift
Når vi integrerer LLM'er i dag, bygger vi ofte meget tætte koblinger (tight coupling) mellem prompten, API-kaldet og vores specifikke backend-logik. Hvis vi ændrer database-skema, skal vi ændre i koden, der fodrer LLM'en med data.

MCP løser dette ved at introducere en **standardiseret protokol** mellem LLM-klienten (f.eks. Claude Desktop eller en lokal kodningsagent) og en række MCP-servere:

```
[ LLM / Agent ] <--- ( MCP Protocol ) ---> [ MCP Server ] <---> [ Vores Database / API / Filer ]
```

Dette betyder, at sprogmodellen selv kan "opdage" (discover) hvilke værktøjer og data, der er tilgængelige på serveren, og selvstændigt kalde dem efter behov. Det gør vores systemer utroligt modulære og fleksible.

### Anvendelse i Gods-Projektet
Hvis vi skulle tage vores Gods-applikation til næste niveau ved hjælp af MCP, ville vi kunne bygge en dedikeret **Engestofte MCP Server**. Denne server kunne eksponere godsets SQL-bookingdatabase og deres e-mail server som MCP-ressourcer. 

Når personalet modtager en mail, ville vores AI-agent selvstændigt kunne forespørge MCP-serveren om ledige datoer i SQL-databasen, sammenholde det med kundenøgle-informationer, og generere et præcist svar – fuldstændig integreret gennem en sikker protokol.

---

## Værktøjer og ressourcer anvendt

* **[Model Context Protocol (MCP) Introduction](/toolbox/mcp/mcp)** - Vores lokale guide til MCP.
* **[MCP Tutorial](/toolbox/mcp/mcp-tutorial)** - Praktisk tutorial til opsætning af en MCP server.
* **Microsoft Teams** - Anvendt til onlinemødet med Mette-Marie og Lise.

---

*Logbog afleveret som en del af eksamensforberedelsen.*
