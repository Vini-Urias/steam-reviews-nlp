# 🎮 Steam Reviews NLP Analysis  
> Análise de Sentimentos e Coerência Texto × Nota em Avaliações da Steam  
> Projeto de Ciência de Dados — ECM514 | Instituto Mauá de Tecnologia (2025)

---

## 🧠 Introdução

Este projeto analisa **avaliações reais de jogos da Steam**, utilizando **técnicas de Processamento de Linguagem Natural (NLP)** para compreender:

- O **foco temático** de cada review (ex.: *gameplay*, *narrative*, *performance*, *community*, etc.);
- O **tom emocional** (positividade/negatividade) através de *sentiment analysis* com o modelo **VADER**;
- A **coerência entre o sentimento do texto e o review_score** atribuído pelo jogador;
- E a **concordância média por jogo**, comparando *tone_score × review_score*.

A partir de dados **crus coletados diretamente via API pública da Steam**, o estudo buscou gerar **insights quantitativos e qualitativos** sobre a percepção dos jogadores em diferentes aspectos dos jogos.

---

## 💾 Base de Dados

| Fonte | Steam Web API |
|--------|----------------|
| Tamanho | 18.548 avaliações |
| Idioma | Inglês (filtrado) |
| Estrutura | `game`, `review`, `review_score`, `tone_score`, `review_focus` |
| Acesso | [Repositório GitHub — Steam Reviews NLP](https://github.com/Vini-Urias/steam-reviews-nlp) |

> Todos os dados foram coletados via script automatizado da API da Steam, garantindo que o projeto utilize **informações brutas e não tratadas previamente**.

---

## 🔬 Metodologia

1. **Coleta de dados crus** via API pública da Steam, com filtro por idioma (inglês);
2. **Pré-processamento textual:** remoção de stopwords, tokenização e normalização de texto;
3. **Classificação temática** por palavras-chave (ex.: *story*, *fps*, *team*, *money*, etc.);
4. **Análise de sentimento (VADER):** cálculo do `tone_score` (de –1 a +1);
5. **Normalização do review_score** (1 = positivo, 0 = negativo);
6. **Integração das métricas:** criação de índices combinados de coerência entre texto × nota;
7. **Visualização interativa:** dashboard em Streamlit para exploração das métricas de cada jogo.

---

## 📈 Resultados Quantitativos

### 🔠 Ocorrências de Palavras-Chave (Positivas vs Negativas)
![Ocorrências de Palavras-Chave](ocorrência%20de%20palavras.png)

> As categorias *narrative*, *gameplay* e *general* concentram a maior parte das menções positivas,  
> enquanto *performance* e *community* exibem o maior volume de críticas negativas, relacionadas a falhas técnicas e comportamento tóxico.

---

## 📊 Análise de Palavras-Chave por Sentimento

✅ **Reviews positivas:** 14.332  ❌ **Negativas:** 4.216  

---

### 🎮 GENERAL (5.053 reviews)
**Positivas:** good (1566), fun (962), love (953), great (891), recommend (664), amazing (561)  
**Negativas:** good (257), bad (207), fun (189), recommend (144), love (130), hate (99)

---

### 🎮 NARRATIVE (2.160 reviews)
**Positivas:** story (1258), world (978), characters (516), feel (496), art (236)  
**Negativas:** story (59), world (55), feel (51), characters (49)

---

### 🎮 CONTENT (2.716 reviews)
**Positivas:** time (854), hours (567), worth (361), long (321), money (253)  
**Negativas:** time (508), hours (309), money (288), content (279), update (146)

---

### 🎮 GAMEPLAY (5.731 reviews)
**Positivas:** fun (1910), gameplay (523), hard (506), combat (322), boss (292)  
**Negativas:** fun (385), gameplay (169), hard (133), boring (113)

---

### 🎮 COMMUNITY (1.506 reviews)
**Positivas:** friends (179), community (139), team (76), online (64)  
**Negativas:** servers (126), toxic (124), team (83), matchmaking (56)

---

### 🎮 PERFORMANCE (1.240 reviews)
**Positivas:** fps (83), graphics (79), fix (57), bug (37)  
**Negativas:** fix (168), fps (54), crash (37), error (37), broken (41)

---

### 🎮 HUMOR (43 reviews)
**Positivas:** xd (9), haha (7), weird (4), funny (2)  
**Negativas:** lmao (2), weird (1)

---

### 🎮 NOSTALGIA (99 reviews)
**Positivas:** classic (29), childhood (9), remember (9), nostalgic (3)  
**Negativas:** since (12), remember (4), nostalgia (1)

---

## 📊 Tom Médio (VADER compound) por Categoria
![Tom Médio por Categoria](tom%20médio%20por%20categoria.png)

> O tom médio é **mais alto em “narrative” e “general”**, demonstrando envolvimento emocional positivo.  
> Já *performance* e *community* permanecem nas posições mais baixas, indicando frustração técnica e social.

---

## 📉 Tom + Review Score médio por Categoria
![Tom + Review Score médio por Categoria](Tom%20e%20Review%20Score%20médio%20por%20categoria.png)

> A correlação entre sentimento e nota mostra **alta coerência em “narrative” e “general”**,  
> e baixa coerência em *performance* e *community*, sugerindo que jogadores criticam fortemente esses aspectos mesmo em jogos bem avaliados.

---

## 🧩 Exemplos Qualitativos

### 🎮 POSITIVO
- **Dota 2:** exemplo de alta coerência entre sentimento e nota — elogios consistentes.  
- **The Witcher 3:** destaca narrativa e ambientação, confirmando tom fortemente positivo.  
- **Dead by Daylight:** demonstra ironia e tom misto apesar de nota positiva.

---

### 🎮 NEUTRO
- **Phasmophobia:** review com tom misto (elogio técnico, crítica funcional).  
- **Rainbow Six Siege:** divergência de sentimento e score.  
- **Dead by Daylight:** review neutra, crítica moderada.

---

### 🎮 NEGATIVO
- **Destiny 2:** exemplo de reviews negativas consistentes, com forte desalinhamento entre texto e nota.  
- **Dead by Daylight:** críticas intensas sobre gameplay e bugs.  
- **Destiny 2 (múltiplas ocorrências):** predominância de frustração e cansaço da comunidade.

---

## 🧭 Conclusão

A análise dos dados **crus** coletados diretamente da Steam mostrou que:

- **“Narrative” e “Gameplay”** concentram as avaliações mais positivas e coerentes;  
- **“Performance” e “Community”** permanecem como as categorias mais críticas, associadas a problemas técnicos e sociais;  
- A **coerência entre review_score e tone_score** varia fortemente entre os jogos, indicando que alguns usuários expressam emoções negativas mesmo em avaliações positivas;  
- O dashboard **Streamlit interativo** permite explorar essas relações por jogo, revelando padrões complexos de percepção entre jogadores e gêneros.

---

## 🧭 Dashboard Interativo (Streamlit)

O projeto inclui um **app interativo em Streamlit**, que permite visualizar:
- Jogos com **maior e menor concordância** entre `review_score` × `tone_score`;
- **Notas médias e tom médio** por jogo;
- **Seleção interativa** de títulos para exibir métricas individuais.

📊 [Acesse o app localmente via Streamlit](http://localhost:8501)  
🌐 [Ou via ngrok (Colab)](https://colab.research.google.com/drive/19ghqgaJOrO7jR74WBzTw3sE_6FPe_emz)

---

## 👥 Equipe

- **Larissa Navarro Pizarro** — RA: 19.02028-7  
- **Lucas Miguel de Matos Negri** — RA: 19.00386-2  
- **Matheus Igino Machado** — RA: 20.01629-8  
- **Vinicius Urias da Cruz** — RA: 20.00601-2  

---

## 🔗 Links

📘 [Notebook no Google Colab](https://colab.research.google.com/drive/19ghqgaJOrO7jR74WBzTw3sE_6FPe_emz?usp=sharing)  
🌐 [Datafólio Online](https://vini-urias.github.io/steam-reviews-nlp/)  
💾 [Repositório GitHub](https://github.com/Vini-Urias/steam-reviews-nlp)
