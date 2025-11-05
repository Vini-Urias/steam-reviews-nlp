# steam-reviews-nlp
Classificação temática e análise de sentimento de avaliações da Steam utilizando NLP e VADER.


# 🎮 Steam Reviews NLP Analysis

**Projeto do 2º Semestre - Ciência de Dados (ECM514)**  
Instituto Mauá de Tecnologia • 2025  
Autores: Larissa Navarro Pizarro, Lucas Miguel de Matos Negri, Matheus Igino Machado, Vinicius Urias da Cruz  

---

## 📘 Descrição do Projeto
Este projeto realiza uma **análise de reviews de jogos da Steam** com foco em **classificação temática** e **análise de sentimento textual**.  
O objetivo é identificar os principais aspectos citados pelos jogadores — como *performance*, *gameplay*, *narrativa* ou *preço* — e medir o **tom emocional** das críticas, correlacionando com a **recomendação (`review_score`)** dada na plataforma.

---

## 🧠 Metodologia
1. **Pré-processamento textual**  
   - Limpeza de HTML, pontuação e *stopwords*  
   - Normalização e tokenização dos textos  

2. **Classificação temática**  
   - Uso de um **dicionário de palavras-chave** para categorizar reviews em temas como *Performance*, *Gameplay*, *Narrative*, *Content*, *Community* e *General*.

3. **Análise de sentimento (VADER)**  
   - Cálculo do tom emocional (`tone_score`) via **NLTK – VADER**  
   - Combinação com o `review_score` para medir coerência entre texto e recomendação.

4. **Visualização e interpretação**  
   - Gráficos de sentimento por categoria  
   - Boxplots de variação emocional  
   - *Word Tone Clouds* filtradas (sem stopwords irrelevantes)  
   - Correlação *texto × nota* por jogo.

---

## 📊 Resultados Principais
- As categorias **Narrative** e **Gameplay** apresentaram os tons médios mais positivos.  
- **Performance** concentrou as críticas negativas (bugs, travamentos, FPS).  
- O índice combinado revelou **jogos com avaliações contraditórias**: recomendados, mas com tom textual negativo — apontando problemas técnicos ignorados pelos jogadores.  
- Visualizações destacaram a coerência emocional por jogo, auxiliando desenvolvedores na priorização de melhorias.

---


## 🧰 Tecnologias
- **Linguagem:** Python 3.10  
- **Bibliotecas:** Pandas, NLTK, WordCloud, Seaborn, Matplotlib  
- **Ambiente:** Google Colab
--- 

🔗 Links do Projeto

Notebook no Google Colab: [Aqui]([https://link-que-será-aberto](https://colab.research.google.com/drive/19ghqgaJOrO7jR74WBzTw3sE_6FPe_emz?usp=sharing))

Base de Dados (Kaggle): [Aqui](https://www.kaggle.com/datasets/andrewmvd/steam-reviews/data)


