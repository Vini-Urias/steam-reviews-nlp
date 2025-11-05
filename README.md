# 🎮 Steam Reviews NLP Analysis  
> Análise de Sentimentos e Foco Temático em Avaliações da Steam  
> Projeto de Ciência de Dados — ECM514 | Instituto Mauá de Tecnologia (2025)

---

## 🧠 Introdução

O projeto analisa **avaliações de jogos da Steam** aplicando técnicas de **Processamento de Linguagem Natural (NLP)**, com o objetivo de identificar:
- O **foco da crítica** (ex.: performance, gameplay, narrativa, conteúdo, comunidade);
- O **tom emocional** das reviews por meio do modelo **VADER**;
- E a **coerência entre o texto e o review_score** da própria Steam.

A proposta busca transformar milhões de avaliações textuais em **insights práticos** para desenvolvedores e plataformas entenderem o que mais agrada ou irrita os jogadores.

---

## 💾 Base de Dados

| Fonte | Kaggle — Steam Reviews Dataset |
|--------|--------------------------------|
| Tamanho | +6 milhões de avaliações |
| Idioma | Inglês |
| Atributos usados | `review`, `review_score`, `review_votes`, `app_name` |
| Link | [Steam Reviews Dataset — Andrew Mvd](https://www.kaggle.com/datasets/andrewmvd/steam-reviews) |

---

## 🔬 Metodologia

1. **Pré-processamento textual:** limpeza, normalização, tokenização e remoção de *stopwords*;  
2. **Classificação temática:** categorização por palavras-chave (ex.: “bug”, “fps”, “story”, “music”);  
3. **Análise de sentimento (VADER):** cálculo de `tone_score` (–1 a +1) e normalização de `review_score`;  
4. **Integração:** criação do índice `combined_sentiment` para medir coerência texto × nota;  
5. **Interpretação:** análise visual e qualitativa das categorias e exemplos.

---

## 📈 Resultados Quantitativos

### 📊 Tom + Review Score médio por Categoria
![Tom + Review Score médio por Categoria](Tom%20e%20Review%20Score%20m%C3%A9dio%20por%20categoria.png)

> As categorias *general* e *narrative* apresentaram os maiores valores médios,  
> enquanto *performance* concentrou os menores escores de sentimento e recomendação.

---

### 💬 Tom Médio (VADER compound) por Categoria
![Tom Médio por Categoria](tom%20m%C3%A9dio%20por%20categoria.png)

> O tom médio mostra uma clara tendência positiva nas categorias *general* e *narrative*,  
> com queda significativa em *performance* e *nostalgia*.

---

### 🔠 Ocorrências de Palavras-Chave (Positivas vs Negativas)
![Ocorrências de Palavras-Chave](ocorr%C3%AAncia%20de%20palavras.png)

> A diferença entre menções positivas e negativas evidencia o impacto emocional das críticas —  
> *general*, *gameplay* e *narrative* são as mais mencionadas positivamente,  
> enquanto *performance* concentra o maior volume de reclamações.

---

## 📊 Análise de Palavras-Chave por Sentimento

✅ **Reviews positivas:** 60,286  ❌ **Negativas:** 12,707  

---

### 🎮 NARRATIVE (8,571 reviews)
**Palavras positivas:** story (4806), characters (2338), world (1659), feel (1533), music (1318)  
**Palavras negativas:** story (610), characters (354), plot (107), art (97)

---

### 🎮 COMMUNITY (3,069 reviews)
**Positivas:** friends (689), multiplayer (456), community (249), team (233)  
**Negativas:** servers (195), online (173), connection (51)

---

### 🎮 GENERAL (20,418 reviews)
**Positivas:** good (6849), great (6249), fun (4924), love (3588)  
**Negativas:** bad (757), boring (255), terrible (246)

---

### 🎮 GAMEPLAY (24,330 reviews)
**Positivas:** fun (8629), gameplay (3681), combat (2262), easy (2053)  
**Negativas:** boring (738), controls (677), enemy (386)

---

### 🎮 CONTENT (10,446 reviews)
**Positivas:** time (3501), worth (2402), money (1285), dlc (1032)  
**Negativas:** time (1013), money (848), dlc (499), price (292)

---

### 🎮 PERFORMANCE (5,623 reviews)
**Positivas:** fps (769), graphics (693), fix (371), bug (163)  
**Negativas:** fix (490), crash (165), broken (198), patch (182)

---

### 🎮 NOSTALGIA (359 reviews)
**Positivas:** classic (105), childhood (50), remember (47)  
**Negativas:** past (12), nostalgia (5)

---

### 🎮 HUMOR (177 reviews)
**Positivas:** xd (49), funny (11), meme (9), haha (4)  
**Negativas:** weird (4), xd (3), sarcastic (1)

---

## 🧩 Exemplos Qualitativos

### 🎮 Altamente Positivo (Elogios Consistentes)
- **Dota 2:** comunidade engajada, mas tóxica — review negativa coerente.  
- **Cities: Skylines:** elogiado pela comunidade ativa e suporte de mods.  
- **Fallout: New Vegas:** bem avaliado, mas com críticas a problemas técnicos.

---

### 🎮 Moderado (Mistura de Elogios e Críticas)
- **Five Nights at Freddy’s:** divertido, porém curto.  
- **Space Hulk: Deathwing:** elogia imersão e ambientação, mas pede otimização.  
- **Rainbow Six Siege:** boa experiência, custo-benefício destacado.

---

### 🎮 Negativo / Inconsistente (Críticas Prevalecem)
- **OPUS: The Day We Found Earth:** bom tom emocional, mas jogabilidade fraca.  
- **Ace of Words:** puzzles interessantes, porém bugados.  
- **Emily Wants To Play:** experiência negativa com erros e sustos excessivos.

---

## 🧭 Conclusão

A análise mostrou que:
- As **categorias “Narrative” e “Gameplay”** geram maior engajamento emocional e sentimento positivo;  
- **“Performance”** concentra reclamações relacionadas a falhas técnicas;  
- Há **inconsistências entre sentimento textual e review_score**, revelando que alguns jogadores recomendam o jogo apesar das críticas.

O método proposto — combinando **palavras-chave temáticas** e **VADER sentiment analysis** — demonstrou ser eficaz para gerar **insights automáticos sobre percepção de jogos** na Steam.

---

## 🔗 Links

📘 [Notebook no Google Colab]([https://colab.research.google.com/drive/SEU_LINK_AQUI](https://colab.research.google.com/drive/19ghqgaJOrO7jR74WBzTw3sE_6FPe_emz?usp=sharing))  
💾 [Dataset — Kaggle (Steam Reviews)](https://www.kaggle.com/datasets/andrewmvd/steam-reviews)  
🌐 [Repositório no GitHub Pages](https://Vini-Urias.github.io/steam-reviews-nlp)

---

## 👥 Equipe

- **Larissa Navarro Pizarro** — RA: 19.02028-7  
- **Lucas Miguel de Matos Negri** — RA: 19.00386-2  
- **Matheus Igino Machado** — RA: 20.01629-8  
- **Vinicius Urias da Cruz** — RA: 20.00601-2  

---

> Projeto desenvolvido para a disciplina **ECM514 — Ciência de Dados**  
> Instituto Mauá de Tecnologia — 2025
