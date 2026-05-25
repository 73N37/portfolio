---
title: "05-LLM-API: Integration af Sprogmodeller i Egne Applikationer"
date: "2026-04-24"
description: "Introduktion til direkte integration af LLM'er via API-kald, system- og user-prompts, asynkron programmering samt design af en AI-drevet vurderingsapp."
showTableOfContents: true
showHero: true
draft: false
tags:
  - "AIDA"
  - "API"
  - "LLM-Integration"
  - "JSON-Output"
  - "Asynkron"
  - "Refleksion"
categories:
  - "Undervisning"
---

Velkommen til den femte logbog på mit portfolio-website for **AIDA**!

Efter at have arbejdet med no-code platforme (som Dify) og kodningsassistenter, tog vi i dag det store spring og kiggede på, hvordan vi **integrerer sprogmodeller programmatisk direkte i vores egen kildekode**. Vi kiggede på rå API-kald, prompt-strukturering, håndtering af asynkron logik og – vigtigst af alt – hvordan vi tvinger en sprogmodel til at returnere **struktureret data (JSON)**, så vores traditionelle software kan parse og anvende svarene.

---

## Praktisk info om sessionen

* **Undervisningsgang:** 5 (Dato: 24/4)
* **Tema:** LLM API-integration
* **Dagens Mål:** Forstå arkitekturen i en LLM-drevet applikation, lære at strukturere API-kald med system- og user-prompts, håndtere timeouts og fejl, samt designe en vurderingsapplikation ud fra en rubric.

---

## Hvad vi gjorde i undervisningen

Sessionen tog udgangspunkt i, at vi som professionelle udviklere skal bygge løsninger, der er robuste og deterministiske. LLM'er er af natur probabilistiske (uforudsigelige), hvilket skaber en fundamental konflikt med traditionel software, der forventer faste datatyper.

Vi gennemgik de vigtigste koncepter til at bygge denne bro:

### 1. API-struktur og Sprogmodellens parametre
Vi arbejdede med de fundamentale parametre i API-kaldet:
* **Temperature:** Hvor kreativ skal modellen være? Til systemintegrationer (hvor vi ønsker præcise, ensartede svar) sættes temperaturen typisk meget lavt (f.eks. `0.0` eller `0.2`).
* **System- og User-prompts:** Vi lærte at separere instruktioner (System: *"Du er en akademisk censor..."*) fra selve dataen (User: *"Her er opgaven: [tekst]"*). Dette beskytter mod prompt-injection og sikrer klar rollefordeling.

### 2. Struktureret Output (JSON Mode & Structured Outputs)
For at vores backend kan læse modellens svar, kan vi ikke bruge rå fritekst. Vi eksperimenterede med at tvinge sprogmodellen til at levere svar i et præcist **JSON-format**. Vi så på, hvordan moderne API'er (såsom OpenAI og Gemini) understøtter faste JSON-skemaer (Structured Outputs / JSON Schema), hvilket garanterer, at modellens svar altid matcher vores definerede datastrukturer.

### 3. Dagens opgave: AI-drevet Vurderingsapp
Vi påbegyndte designet af en applikation, der skal kunne tage en studerendes opgavebesvarelse som input, sammenligne den med en faglig **rubric** (vurderingskriterier), og automatisk generere en struktureret karakter og feedback i JSON-format. 

---

## Refleksionsartikel: Udfordringer ved at koble det deterministiske med det probabilistiske

At bygge et system, hvor en LLM er en central komponent, er markant anderledes end at bygge traditionelle REST API'er.

### Uforudsigelighed og Parse-fejl
Selv med lav temperatur og strenge JSON-instruktioner kan en model en sjælden gang finde på at returnere ugyldig JSON eller udelade et påkrævet felt. Vores software skal designes defensivt:
* Vi skal altid pakke vores parsere ind i `try-catch` blokke.
* Vi skal have fallback-strategier (fx gen-forsøg med en justeret prompt, hvis parseren fejler).

### Håndtering af Timeouts og Latency
En traditionel databaseforespørgsel tager få millisekunder. Et LLM API-kald tager ofte flere sekunder, da modellen skal generere svar token for token. Dette stiller store krav til vores backend-arkitektur:
* Vi skal programmere fuldstændig asynkront.
* Vi skal overveje UX (brugergrænsefladen) – brugere kan ikke stirre på en død skærm i 10 sekunder; vi skal implementere loading-states eller streaming-effekter.

### Økonomiske overvejelser og Rate Limits
Hvert kald koster penge baseret på tokens (både input- og output-tokens). Vi skal tænke over optimering og undgå unødvendige kald (f.eks. ved at cache svar eller deduplikere ens requests). Derudover skal vi håndtere *Rate Limits* (begrænsninger på antal kald per minut), hvilket kræver kø-systemer eller kontrolleret backoff-logik i vores kode.

### Konklusion
Dagens session var en øjenåbner i forhold til, hvad det reelt kræver at bygge produktionsegnet AI-software. Det er let at skrive et hurtigt script, der kalder OpenAI's API, men at bygge en robust, asynkron backend med fejlhåndtering, skemavalidering og optimal token-økonomi er en helt anden disciplin. Jeg ser frem til at implementere vurderingsappen i kode i næste modul!

---

## Værktøjer og ressourcer anvendt

* **[OpenAI API / Gemini API](https://platform.openai.com/)** - API'er anvendt til rå integration.
* **[Tjekliste for LLM-integration](/toolbox/llm-integration/tjekliste)** - Den lokale tjekliste for god API-praksis.
* **[Ordliste](/toolbox/ordliste)** - Begrebsafklaring for sprogmodel-integration.

---

*Logbog afleveret som en del af eksamensforberedelsen.*
