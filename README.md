# Análise de Sentimentos em Avaliações de Disciplinas (NLP)

**Monografia MBA em Ciência de Dados (MBA - ICMC/USP)** - *Um estudo de caso sobre a aplicação de modelos Transformers (BERT) para classificar feedback de alunos no ensino superior.*

## Sobre o Projeto
Este projeto foi desenvolvido como Trabalho de Conclusão de Curso (TCC) para o MBA em Ciência de Dados do **ICMC-USP**. O objetivo foi automatizar a análise de avaliações de disciplinas, transformando milhares de comentários textuais não estruturados em *insights* acionáveis para a gestão acadêmica.

O estudo comparou o desempenho de modelos **Multilíngues** versus modelos **Treinados em Português (PT-BR)** na tarefa de classificação de sentimentos (Positivo, Negativo e Neutro).

### Principais Objetivos
* Automatizar a leitura de um grande volume de comentários (Dataset com ~16.500 registros de 2017 a 2023).
* Validar a hipótese de que modelos nativos (BERTimbau) superam modelos multilíngues (XLM-RoBERTa) em contextos específicos.
* Criar um pipeline de rotulagem de dados assistido por **LLMs** para otimizar o tempo de anotação.

---

## Metodologia e Pipeline
O projeto seguiu um fluxo rigoroso de Ciência de Dados:

1. **Pré-processamento:** Limpeza de texto, remoção de stopwords, tokenização e tratamento de dados ausentes.
2. **Rotulação Híbrida (Inovação):** Para criar o *Ground Truth*, foi utilizada uma estratégia de pré-classificação com **LLM (Gemini)** seguida de validação humana manual em uma amostra representativa.
3. **Modelagem (Fine-Tuning):** Ajuste fino de modelos pré-treinados da arquitetura Transformer:
    * **BERTimbau** (Base e Large) - Treinado em PT-BR.
    * **XLM-RoBERTa** (Base e Large) - Multilíngue.

---

## Resultados Alcançados
O modelo **BERTimbau-Large** apresentou o melhor desempenho geral, confirmando que o pré-treinamento na língua alvo captura melhor as nuances e gírias do ambiente acadêmico brasileiro.

| Modelo | Acurácia | F1-Score | MCC |
| --- | --- | --- | --- |
| **BERTimbau-Large** | **90,67%** | **90,37%** | **0,8450** |
| BERTimbau-Base | 88,00% | 87,52% | 0,8002 |
| XLM-RoBERTa-Base | 83,33% | 76,91% | 0,7333 |
| XLM-RoBERTa-Large | 81,33% | 74,92% | 0,7018 |

Fonte: Tabela de resultados da monografia.
 
**Insight:** A análise da matriz de confusão mostrou que a maior dificuldade dos modelos reside na distinção entre a classe **Neutra** e as demais, devido à subjetividade e ironia presentes nos comentários.

---

## Referência Bibliográfica
Caso utilize este trabalho ou parte do código, por favor cite:

PREVIATO, E. V. **Análise de sentimentos em avaliações de disciplinas: um estudo de caso no ensino superior**. 2025. 44 p. Monografia (MBA em Ciências de Dados) - Instituto de Ciências Matemáticas e de Computação, Universidade de São Paulo, São Carlos, 2025.

---

## Autor
**Erick Vansim Previato** *Cientista de Dados | Especialista em IA*
[https://www.linkedin.com/in/erickpreviato](https://www.linkedin.com/in/erickpreviato)

---

Este projeto foi orientado pelo Prof. Dr. Wallace Correa de Oliveira Casaca.