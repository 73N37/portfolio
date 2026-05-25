---
title: "02-RAG: Retrieval Augmented Generation og Etablering af Chatbots"
date: "2026-04-13"
description: "Introduktion til RAG-arkitekturen, hands-on erfaring med Dify.ai, samt optimering af egne datakilder ved konvertering af studieordningen til markdown."
showTableOfContents: true
showHero: true
draft: false
tags:
  - "AIDA"
  - "RAG"
  - "Dify"
  - "Embeddings"
  - "Chatbots"
  - "Refleksion"
categories:
  - "Undervisning"
---

Velkommen til den anden logbog på mit portfolio-website for **AIDA (AI-Driven Applications)**! 

Dette modul markerede vores første rigtige dyk ned i en af de mest anvendte arkitekturer inden for moderne sprogmodel-applikationer: **Retrieval Augmented Generation (RAG)**. Vi gik fra teori til praktisk anvendelse ved at bygge en velfungerende chatbot baseret på vores egen studieordning.

---

## Praktisk info om sessionen

* **Undervisningsgang:** 2 (Dato: 13/4)
* **Tema:** Retrieval Augmented Generation (RAG)
* **Dagens Mål:** Forstå teorien bag RAG (embeddings, vector-søgning og retrieval-koncepter), samt sammenligne ChatGPT CustomGPT, CustomGPT.ai og Dify.ai som platforme.

---

## Hvad vi gjorde i undervisningen

Undervisningen var stærkt praksisorienteret og tog udgangspunkt i en solid introduktion til, hvorfor RAG er nødvendigt. Vi diskuterede, hvordan LLM'er har en begrænset vidensbase og lider under "hallucinationer", og hvordan RAG løser dette ved at agere som en "open book"-eksamen, hvor modellen kan slå op i eksterne dokumenter, før den genererer sit svar.

Vi arbejdede med tre primære tilgange til RAG-opsætning:
1. **ChatGPTs CustomGPT:** Super hurtigt at opsætte, men meget begrænset i forhold til integrationer og kontrol.
2. **customgpt.ai:** God brugervenlighed og stærk out-of-the-box søgning, men relativt lukket.
3. **Dify.ai:** En utrolig stærk og fleksibel open-source LLM-applikationsudviklingsplatform. Det var her, vi lagde vores primære fokus.

### Den praktiske case: Studieordningen
For at afprøve teknologien i praksis byggede vi en chatbot, der skulle svare på spørgsmål om vores **studieordning** (`dat_cba_studieordning_2024.pdf`). 

Her lærte vi en vigtig lektie: **Data-forberedelse er alt**. Hvis vi blot uploader en rå PDF med kompliceret layout og tabeller, bliver retrieval-kvaliteten ofte ringe. Derfor konverterede vi PDF'en til **Markdown**, hvilket gjorde det langt nemmere for Dify's parser at opdele (chunke) teksten meningsfuldt og generere præcise embeddings.

---

## Refleksionsartikel: Fordele, ulemper og arkitektoniske overvejelser ved RAG

Opsætningen af vores Dify-chatbot gav anledning til dybere overvejelser omkring, hvornår RAG er den rette løsning.

### Fordele ved RAG
* **Dynamisk viden uden finetuning:** Vi kan opdatere chatbotten blot ved at udskifte eller tilføje markdown-filer i Dify. Det koster en brøkdel af, hvad det ville koste at gen-træne eller finetune en hel model.
* **Højere troværdighed (Mitigering af hallucinationer):** Modellen tvinges til at svare ud fra det fremsøgte kontekst. Hvis svaret ikke står i dokumenterne, kan vi instruere modellen i at sige "Det ved jeg desværre ikke", frem for at den opdigter et svar.
* **Kildeangivelser:** Systemer som Dify tillader os at se præcis hvilke chunks (tekststykker), der blev brugt til at generere svaret, hvilket er essentielt for revision og tillid.

### Faldgruber og ulemper
* **"Garbage In, Garbage Out":** Hvis datakilden er ustruktureret eller fyldt med støj, bliver søgeresultaterne dårlige, og dermed bliver LLM'ens svar også ukorrekte.
* **Chunking-strategier er svære:** Hvordan deler man en tekst op? For store chunks udvander relevansen. For små chunks mister vigtig kontekst (fx overskrifter). Dette er en disciplin i sig selv.
* **Sikkerhed og adgangsstyring:** Hvis man bygger en virksomhedsløsning, skal man sikre, at følsomme data kun fremsøges til brugere, der faktisk har rettigheder til at se dem.

### Konklusion
Dify.ai viste sig at være et utroligt kraftfuldt værktøj. Selvom platformen abstraherer meget af den rå kode væk, tvinger den os stadig til at tænke som systemudviklere i forhold til datastruktur, prompting-strategier og evalueringsparametre. Vores færdige chatbot demonstrerede tydeligt, at en velforberedt markdown-kilde resulterer i præcise og pålidelige svar.

---

## Værktøjer og ressourcer anvendt

* **[Dify.ai](https://dify.ai/)** - Udviklingsplatform for LLM-applikationer.
* **[customgpt.ai](https://customgpt.ai/)** - Alternativ RAG-platform anvendt til komparativ analyse.
* **[Dify.ai Video Tutorial](https://www.youtube.com/watch?v=dHJictxN2ZU)** - En rigtig god guide til at forstå flows og datakilder i Dify.

---

*Logbog afleveret som en del af eksamensforberedelsen.*
