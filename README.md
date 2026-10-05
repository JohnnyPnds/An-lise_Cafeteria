# ☕ CoffeeLab: Análise de Dados e Otimização Operacional

> Estudo de caso de análise exploratória, tratamento e inteligência de dados aplicada à operação de uma rede de cafeterias, com foco em diagnóstico financeiro, experiência do cliente e alavancas de eficiência operacional.

---

## 📌 Contexto do Projeto

Projeto acadêmico desenvolvido para a disciplina de **Análise de Dados** do curso de **Ciência da Computação** da **Universidade Presbiteriana Mackenzie** (Semestre 2026/2, Prof. Bruno Mascaro), avaliado com **nota 9,0/10**.

A base contempla **1.909 registros operacionais** da rede *CoffeeLab* distribuídos entre **8 unidades**, cobrindo o período de 15/06/2026 a 06/09/2026 nos turnos da Manhã, Tarde e Noite, com 17 variáveis de negócio (faturamento, clientes, promoções, tempo de espera, avaliação, custos e métricas climáticas).

---

## 🛠️ Pipeline de Tratamento dos Dados (Data Cleaning)

Antes das análises, realizou-se a auditoria e saneamento dos dados para garantir integridade analítica:
- **Padronização Categórica:** Unificação das grafias da loja `"centro"` e `"Centro"` em uma única unidade.
- **Correção de Outliers e Digitação:**
  - Avaliação de `46.0` corrigida para `4.6` (escala original de 1 a 5).
  - Tempo de espera de `92.0 min` corrigido para `9.2 min` após validação de inconsistência decimal.
- **Valores Ausentes:** Preenchimento com base na mediana da loja (avaliação na linha 102 preenchida com `4.4`) e custo de promoção preenchido com `0.0`.
- **Deduplicação:** Remoção de linha duplicada (registro 1910 espelhado da linha 302).
- **Engenharia de Variáveis (Feature Engineering):**
  - `sobrecarga`: Relação entre quantidade de clientes atendidos e o quadro de funcionários no turno.
  - `faturamento_liquido`: Diferença entre o faturamento bruto e o custo promocional alocado.

---

## 🔍 Principais Insights e Relações

1. **Trade-off "Vende Bem x Atende Mal" (Vila Olímpia):**  
   A unidade da Vila Olímpia lidera o faturamento médio da rede (R$ 3.179), porém registra a **pior avaliação média (4,13)** e o **maior tempo de fila (10,56 min)**, puxada por uma sobrecarga crítica de 22 clientes/funcionário (contra a média de ~13 das demais). A correlação entre tempo de espera e avaliação é de **r = -0,73**.
   
2. **Ineficiência Financeira das Promoções:**  
   As campanhas promocionais geram aumento de fluxo (+17,5% de clientes), mas corroem o ticket médio (cai de R$ 32,44 para R$ 28,61). Ao descontar o custo direto da campanha, o **faturamento líquido médio sem promoção (R$ 2.754) é superior ao com promoção (R$ 2.689)**.

3. **Assimetria Temporal de Receita:**  
   O turno da noite concentra o maior faturamento e fluxo de pedidos (média de R$ 3.871/turno), enquanto a manhã apresenta faturamento médio de apenas R$ 1.821, revelando ociosidade no início do dia.

---

## 💡 Recomendações Estratégicas

- **1. Reestruturação de Escala (Vila Olímpia & Santana):** Redimensionar o quadro de funcionários nos horários de pico para mitigar a sobrecarga, reduzir a fila de espera para patamares médios (6-7 min) e recuperar a nota de avaliação dos clientes.
- **2. Repaginação do Modelo Promocional:** Suspender descontos lineares generalizados no início da semana que geram prejuízo líquido. Priorizar combos de produtos com maior margem ou fidelização sem canibalização de ticket.
- **3. Ativação de Receita Matinal:** Criação de cardápios executivos matinais, combos de café da manhã rápido e programas corporativos para elevar a tração no período das manhãs.

---

## 👥 Equipe do Projeto

Projeto realizado em grupo pelos alunos de Ciência da Computação:
- **João Santos**
- **Bruno Maia**
- **Heitor Do Vale**
- **Vinicius Zanotto**
