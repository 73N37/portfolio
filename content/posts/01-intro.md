---
title: "01-Intro: Kursusintroduktion og Portfolio-refleksioner"
date: "2026-04-10"
description: "Introduktion til AIDA Spring 2026 valgfaget, opsætning af portefølje-website med Hugo & Blowfish, samt refleksioner over AI i softwareudvikling."
showTableOfContents: true
showHero: true
draft: false
tags:
  - "AIDA"
  - "Hugo"
  - "Blowfish"
  - "Portfolio"
  - "Refleksion"
  - "Softwareudvikling"
  - "AI"
categories:
  - "Undervisning"
  - "Eksamen"
---

Velkommen til den første logbog på mit portfolio-website for valgfaget **AIDA (AI-Driven Applications) Spring 2026**! 

Dette website vil fungere som min primære dokumentationsplatform, hvor jeg gennemgår de teorier, teknologier og praktiske cases, som vi arbejder med i løbet af semestret. Denne første artikel opsummerer vores introduktionsgang den **10. april 2026**, samt mine personlige refleksioner om kunstig intelligens i moderne softwareudvikling.

---

## Praktisk info om sessionen

* **Undervisningsgang:** 1 (Dato: 10/4)
* **Tema:** Kursusintro + Portfolio-etablering
* **Dagens Mål:** Introduktion til faget, forventningsafstemning, forståelse af LLM-arkitekturer og opsætning af et statisk portfolio-website ved hjælp af Hugo og Blowfish-temaet.

---

## Hvad vi gjorde i undervisningen

Sessionen startede med en overordnet introduktion til valgfaget AIDA, dets struktur, samt kravene til den kommende eksamen. Vi diskuterede, hvordan AI-drevne applikationer adskiller sig fra traditionel software, og hvordan Large Language Models (LLM’er) integreres som centrale komponenter i moderne softwarearkitektur.

Derefter gik vi over til det praktiske arbejde: **etablering af vores eget portfolio-website**.

### 1. Opsætning med Hugo & Blowfish
Vi benyttede static site generatoren **Hugo** på grund af dens ekstreme hastighed og fleksibilitet. Som designskabelon valgte vi **Blowfish** – et moderne og visuelt stærkt tema, der understøtter både mørkt/lyst tema, tags, kategorier og en super ren æstetik.

De grundlæggende trin, vi gennemgik, var:
* Initialisering af et nyt Hugo-site.
* Integration af Blowfish-temaet som et Git-submodul.
* Konfiguration af `hugo.toml` og opsætning af temaparametre under `config/_default/`.

### 2. Versionsstyring & Deployment
For at sikre en professionel arbejdsgang blev websitet koblet op på et **GitHub-repository**. Vi konfigurerede en **GitHub Actions workflow**, der automatisk bygger og deployer sitet, hver gang vi pusher nye ændringer til vores repository. Dette sikrer en fuldstændig automatiseret CI/CD-pipeline.

---

## Refleksionsartikel: AI's rolle i fremtidens softwareudvikling

Som en del af dagens opgave har jeg formuleret mine tanker og refleksioner over, hvordan kunstig intelligens og LLM'er vil forme vores fremtid som softwareudviklere.

### Forventninger til AI i softwareudvikling
AI er ikke længere blot en avanceret autoudfyldelse i vores IDE'er; det er ved at blive en aktiv samarbejdspartner. Mine primære forventninger til AI-værktøjer (såsom GitHub Copilot, ChatGPT og mere specialiserede kodningsagenter) er:

1. **Hurtigere prototyping og reduceret boilerplate:** AI udmærker sig ved at generere standardkode, opsætte test-suiter og skrive triviel kode. Dette frigør tid til at fokusere på systemarkitektur, forretningslogik og mere komplekse problemløsninger.
2. **Lavere barriere for ny læring:** Med AI-assistenter kan man hurtigt sætte sig ind i nye frameworks eller programmeringssprog, da man har en interaktiv tutor ved hånden hele tiden.
3. **Agenter frem for simple chatbots:** Vi bevæger os fra simple prompt-baserede systemer mod agentiske workflows (f.eks. ved brug af MCP - Model Context Protocol), hvor AI'en selvstændigt kan udføre opgaver i vores terminaler og redigere filer.

### Fordele og faldgruber
Selvom potentialet er enormt, er der kritiske overvejelser, man skal gøre sig:

* **Faren for "Code Bloat" og teknisk gæld:** Fordi det er så let at generere kode, risikerer vi at introducere massive mængder uoverskuelig kode, som ingen reelt forstår. Det stiller større krav til vores evne til at læse, revidere og kvalitetssikre kode (Code Review).
* **Mangel på dyb forståelse:** Hvis man blindt accepterer AI'ens forslag, risikerer man at miste evnen til at fejlsøge og forstå de fundamentale mekanismer i koden.
* **Developer-in-the-Loop:** Det er afgørende, at udvikleren forbliver den styrende part. AI skal ses som en intelligent assistent, men det er mennesket, der bærer ansvaret for sikkerhed, arkitektonisk integritet og UX.

### Konklusion
Min overordnede forventning til AIDA-faget er at lære, hvordan vi designer robuste systemer, der udnytter AI'ens styrker, uden at gå på kompromis med softwarekvalitet og sikkerhed. Vi skal gå fra at være traditionelle "kodere" til at blive arkitekter og "directors", der formår at orchestrere AI-agenter og sprogmodeller til at bygge fremtidens intelligente software.

---

## Værktøjer og ressourcer anvendt

* **[Hugo](https://gohugo.io/)** - Static Site Generator.
* **[Blowfish Theme](https://blowfish.page/)** - Tema til porteføljen.
* **[What is an LLM? (YouTube)](https://www.youtube.com/watch?v=LPZh9BOjkQs)** - Fremragende introduktionsvideo til Large Language Models af Andrej Karpathy.
* **[Hugo Tutorial](/toolbox/portfolio)** - Den lokale guide til at mestre portefølje-opsætningen.

---

*Logbog afleveret som en del af eksamensforberedelsen for kandidat posts.*
