---
title: "03-RAG-demo: Evaluering, Promptdesign og Datakvalitet"
date: "2026-04-17"
description: "Erfaringer med optimering af retrieval-kvalitet, justering af promptdesign for RAG og etablering af en lokal chatbot på portfolio-websitet."
showTableOfContents: true
showHero: true
draft: false
tags:
  - "AIDA"
  - "RAG"
  - "Promptdesign"
  - "Datakvalitet"
  - "Dify"
  - "Portfolio"
categories:
  - "Undervisning"
---

Velkommen til min tredje logbog på portfolio-websitet for **AIDA**!

Efter vores introduktion til RAG-arkitekturen i modul 02, fokuserede denne undervisningsgang på den sværeste del af RAG-udvikling: **optimering af retrieval-kvalitet, promptdesign og praktisk evaluering**. Vi brugte sessionen på at bygge videre på vores cases og integrere en fungerende chatbot-løsning på vores eget portfolio-website.

---

## Praktisk info om sessionen

* **Undervisningsgang:** 3 (Dato: 17/4)
* **Tema:** RAG demo og gennemgang
* **Dagens Mål:** Lære at evaluere retrieval-kvalitet, optimere datakilder (konvertering til Markdown), finpudse prompts til RAG og etablere en chatbot på vores eget portfolio-site.

---

## Hvad vi gjorde i undervisningen

Modulet startede med en grundig gennemgang af forskellige holds RAG-chatbots. Vi så på konkrete eksempler på, hvornår retrieval fungerede godt, og hvornår det fejlede. Dette førte til en diskussion om, hvordan man strukturerer data mest hensigtsmæssigt.

### 1. Fra PDF til Markdown (Dataoptimering)
Vi erfarede hurtigt, at traditionelle PDF'er er et mareridt for tekst-chunking algoritmer. PDF-formater indeholder headers, footers, to-kolonne layouts og tabeller, der bliver fuldstændig rodet sammen, når de trækkes ud som rå tekst. 

Gennem praktiske øvelser lærte vi at:
* Konvertere datakilder til rent **Markdown**-format.
* Bruge `#`, `##` og `###` overskrifter aktivt til at afgrænse afsnit, da moderne parsere kan bruge disse strukturer til at adskille chunks.
* Strukturere tabeller i markdown, så semantikken bevares.

### 2. Promptdesign til RAG
Vi arbejdede med at finpudse system-prompts i Dify. En klassisk RAG-prompt skal ikke bare sige *"Svar på brugerens spørgsmål"*. For at opnå høj pålidelighed skal system-prompten struktureres strengt:
* **Kontekst-afgrænsning:** Instruer modellen i *kun* at svare baseret på den vedlagte kontekst.
* **Sikkerhedsmekanisme:** Definer et standardsvar (f.eks. *"Jeg kan desværre ikke finde svar på dette i studieordningen"*), hvis informationen ikke findes i retrieval-materialet.
* **Tone og format:** Specificer hvordan svaret skal formateres (fx med punkttegn for bedre læsbarhed).

### 3. Integration af chatbot på websitet
Som det praktiske slutprodukt fik vi integreret vores RAG-chatbot direkte på vores eget statiske Blowfish portfolio-site. Dette blev gjort ved at hente en indlejret widget (embed script) fra Dify.ai, hvilket skabte en fuldstændig integreret og interaktiv oplevelse for de besøgende.

---

## Refleksionsartikel: RAG er ikke en 'Set-and-Forget' teknologi

At bygge et velfungerende RAG-system kræver en agil og iterativ proces. Min vigtigste læring fra denne gang er, at RAG på ingen måde er en statisk løsning. Det er en løbende optimeringsproces.

### Evalueringsudfordringen
Hvordan ved vi reelt, om vores chatbot svarer rigtigt? I traditionel softwareudvikling skriver vi unit-tests med forventede outputs. I LLM-udvikling er outputtet flydende. Vi er nødt til systematisk at teste med en række faste spørgsmål og manuelt vurdere:
1. **Retrieval Precision:** Fandt systemet de korrekte dokumenter frem?
2. **Generation Fidelity:** Svarede sprogmodellen sandfærdigt ud fra de fremsøgte dokumenter, eller digtede den videre (hallucination)?

### Promptdesignets magt og begrænsninger
En lille ændring i system-prompten kan fuldstændig ændre chatbotten fra at være ekstremt hjælpsom til at være alt for restriktiv. Vi oplevede eksempler, hvor modellen nægtede at svare på helt legitime spørgsmål, fordi system-prompten instruerede den for hårdt i ikke at svare på noget uden for konteksten. Det handler om at finde den rette balance mellem kreativitet og præcision.

### Konklusion
Dagen gav os et solidt indblik i virkeligheden som "AI-udviklere". Selvom værktøjer som Dify gør det legende let at uploade filer og få en chatbot op at køre på 10 minutter, så ligger den reelle ingeniørmæssige værdi i datapræpareringen, den kontinuerlige prompt-justering og evalueringen af retrieval-kvaliteten. Det er her, vi som professionelle softwareudviklere skal lægge vores fokus fremover.

---

## Værktøjer og ressourcer anvendt

* **[Dify.ai](https://dify.ai/)** - Til hosting og finpudsning af prompten.
* **Markdown Guideline** - Regler for god datastrukturering til LLM retrieval.
* **Blowfish Integration** - Dify widget integreret på vores portfolio-site.

---

*Logbog afleveret som en del af eksamensforberedelsen.*
