# Projeto_Vext_Fintech
# Vext — Plataforma de Inteligência Financeira com IA

O **Vext** é um projeto académico de FinTech focado na criação de uma plataforma de inteligência financeira pessoal para investidores portugueses.

O projeto combina finanças pessoais, análise de investimentos, fiscalidade portuguesa, planeamento FIRE e agentes de Inteligência Artificial numa plataforma modular, pensada para apoiar decisões financeiras de forma mais estruturada, privada e contextualizada.

> Protótipo académico desenvolvido no âmbito da unidade curricular de FinTech.
> Este repositório documenta o conceito, a arquitetura, o enquadramento técnico e a visão de produto do projeto Vext.

---

## Visão Geral

O Vext foi concebido como uma plataforma de inteligência financeira pessoal para utilizadores que pretendem acompanhar os seus investimentos, compreender implicações fiscais, simular objetivos de independência financeira e obter insights personalizados com apoio de Inteligência Artificial.

A ideia principal do projeto é permitir que um investidor consiga responder a questões como:

* Quão perto estou da independência financeira?
* Qual é o impacto fiscal de vender parte do meu portefólio?
* Como é que mais-valias, dividendos e criptoativos influenciam a minha situação fiscal?
* O meu portefólio está alinhado com os meus objetivos financeiros de longo prazo?
* Que riscos, oportunidades ou ineficiências existem na minha estratégia de investimento?

O Vext procura juntar dados financeiros, regras fiscais, simulações e IA num único sistema integrado.

---

## Problema

Muitos investidores individuais utilizam várias ferramentas separadas para gerir a sua vida financeira:

* folhas de cálculo para acompanhar investimentos;
* plataformas de corretoras para consultar transações;
* websites para obter dados de mercado;
* calculadoras externas para simular independência financeira;
* pesquisa manual para compreender regras fiscais;
* ferramentas genéricas de IA para explicações financeiras.

Esta fragmentação dificulta a obtenção de uma visão completa e contextualizada da situação financeira do investidor.

No caso português, o problema torna-se ainda mais específico, porque as decisões de investimento são fortemente influenciadas pelas regras fiscais nacionais, como mais-valias, dividendos, criptoativos, FIFO, englobamento e declaração em sede de IRS.

O Vext foi criado para explorar como uma plataforma de inteligência financeira poderia ajudar a resolver este problema, combinando dados, lógica fiscal, simulações financeiras e agentes de IA.

---

## Solução Proposta

O Vext propõe uma plataforma **local-first**, onde os dados financeiros do utilizador são tratados com foco na privacidade e na organização local da informação.

A plataforma assenta em cinco pilares principais:

1. **Acompanhamento de Portefólio**
   Registo e análise de ativos, transações, preços e desempenho.

2. **Motor Fiscal Português**
   Cálculo e análise de eventos fiscais relacionados com investimentos, incluindo mais-valias, FIFO, dividendos, criptoativos e cenários de IRS.

3. **Planeamento FIRE**
   Simulação de cenários de independência financeira, incluindo FIRE number, projeções, taxa de levantamento e análise de incerteza.

4. **Motor de Valuation**
   Apoio à análise de valor intrínseco através de métodos como Discounted Cash Flow, múltiplos financeiros e rácios.

5. **Agente Financeiro com IA**
   Assistente inteligente capaz de usar ferramentas, aceder a dados estruturados e gerar análises contextualizadas, reduzindo respostas genéricas ou pouco fundamentadas.

---

## Funcionalidades Principais

### Gestão de Portefólio

* Registo de ativos e transações
* Visão geral do portefólio
* Análise de alocação
* Integração com dados históricos de mercado
* Armazenamento local da informação

### Fiscalidade Portuguesa

* Cálculo de mais-valias com lógica FIFO
* Identificação de eventos fiscais
* Análise de dividendos e rendimentos de investimento
* Consideração de criptoativos
* Apoio à preparação de informação para IRS
* Avaliação do impacto fiscal nas decisões de investimento

### Planeamento FIRE

* Cálculo do valor necessário para independência financeira
* Projeções de longo prazo
* Simulações com diferentes pressupostos
* Taxas de levantamento
* Análise líquida após impacto fiscal
* Simulação de incerteza através de Monte Carlo

### Valuation

* Estimativa de valor intrínseco
* Modelo de Discounted Cash Flow
* Avaliação relativa por múltiplos
* Agregação de sinais de valuation
* Apoio à análise de decisões de investimento

### Agente de IA

* Assistente financeiro baseado em modelos de linguagem
* Raciocínio apoiado por ferramentas
* Análise contextualizada do portefólio
* Explicação de resultados financeiros
* Separação entre cálculos objetivos e respostas em linguagem natural
* Redução de alucinações através de módulos de cálculo controlados

### Camada de Memória

* Memória contextual sobre objetivos e preferências do utilizador
* Base de conhecimento pessoal
* Possível integração com fluxos de RAG
* Personalização progressiva das análises

---

## Blocos de Desenvolvimento

O projeto foi estruturado em nove blocos de desenvolvimento.

### 1. Foundation

Definição da estrutura inicial do projeto, organização do repositório, documentação, configuração do ambiente e planeamento arquitetural.

### 2. Dados e Persistência

Planeamento da camada de dados local, schema da base de dados, operações CRUD, dados iniciais e lógica de cache de preços.

### 3. Motor Fiscal Português

Definição da lógica fiscal, cálculo de mais-valias, aplicação de FIFO, identificação de eventos fiscais e integração com transações do utilizador.

### 4. Motor FIRE

Desenvolvimento conceptual dos cálculos de independência financeira, FIRE number, projeções, análise líquida e simulações de Monte Carlo.

### 5. Motor de Valuation

Planeamento dos modelos de valor intrínseco, DCF, avaliação relativa e agregação de sinais financeiros.

### 6. Dashboard

Conceção da interface em Streamlit, incluindo áreas dedicadas ao portefólio, FIRE, IRS e valuation.

### 7. Agente de IA

Desenho de um agente financeiro com IA, baseado em ferramentas, raciocínio controlado e integração modular com os motores da plataforma.

### 8. Camada de Memória

Planeamento de memória contextual, armazenamento de conhecimento e recuperação de informação para análises mais personalizadas.

### 9. Produto Final

Definição de relatórios, exportações, alertas, automações e melhorias orientadas a uma possível evolução do projeto para produto digital.

---

## Arquitetura Proposta

O Vext segue uma arquitetura modular, pensada para separar responsabilidades entre diferentes componentes do sistema.

```text
vext/
├── app/
│   └── dashboard/
├── data/
│   └── database/
├── engines/
│   ├── tax/
│   ├── fire/
│   └── valuation/
├── agents/
│   └── financial_agent/
├── memory/
│   └── knowledge_base/
├── services/
│   ├── market_data/
│   └── reporting/
├── docs/
└── tests/
```

### Camadas Principais

* **Camada de Dados** — armazena utilizadores, ativos, transações, preços e resultados calculados.
* **Camada de Motores** — executa cálculos fiscais, simulações FIRE e modelos de valuation.
* **Camada de Agentes** — utiliza IA e ferramentas para gerar análises financeiras.
* **Camada de Dashboard** — disponibiliza a interface de utilização.
* **Camada de Memória** — guarda contexto, preferências e conhecimento relevante.
* **Camada de Reporting** — gera relatórios, exportações e outputs estruturados.

---

## Tecnologias e Conceitos

O projeto foi desenhado com base nas seguintes tecnologias e conceitos:

* **Python** — linguagem principal
* **Streamlit** — dashboard e interface
* **SQLite** — armazenamento local
* **Pandas** — manipulação e análise de dados
* **yfinance** — dados financeiros de mercado
* **CoinGecko API** — dados de criptoativos
* **Financial Modeling Prep API** — métricas financeiras e dados de empresas
* **LangGraph** — desenho de fluxos agentic AI
* **LLMs** — camada de assistente inteligente
* **Ollama** — experimentação com modelos locais
* **ChromaDB** — base vetorial para memória/RAG
* **Poetry** — gestão de dependências
* **Simulação de Monte Carlo** — modelação de incerteza financeira

---

## Componente de Inteligência Artificial

Uma das componentes centrais do Vext é o agente financeiro com IA.

O objetivo do agente não é substituir aconselhamento financeiro profissional, mas sim apoiar o utilizador através de análises mais claras, contextualizadas e fundamentadas.

O agente foi pensado para:

* explicar alterações no portefólio;
* identificar riscos e oportunidades;
* resumir impactos fiscais;
* responder a questões sobre cenários FIRE;
* utilizar ferramentas de cálculo em vez de gerar respostas especulativas;
* produzir insights personalizados com base nos dados do utilizador.

A camada de IA foi desenhada com uma arquitetura baseada em ferramentas, onde o modelo de linguagem pode recorrer a motores específicos de cálculo antes de gerar uma resposta final.

Esta abordagem melhora a fiabilidade, a explicabilidade e a utilidade das respostas.

---

## Foco na Fiscalidade Portuguesa

Um dos principais fatores diferenciadores do Vext é o seu foco no contexto fiscal português.

O projeto explora a integração de regras fiscais nacionais na análise de investimentos, incluindo:

* lógica FIFO para cálculo de mais-valias;
* identificação de eventos tributáveis;
* dividendos;
* criptoativos;
* enquadramento em sede de IRS;
* impacto fiscal no planeamento FIRE;
* projeções líquidas do portefólio.

Este foco torna o projeto especialmente relevante para investidores portugueses, uma vez que muitas ferramentas internacionais de finanças pessoais não contemplam a fiscalidade portuguesa com detalhe suficiente.

---

## Planeamento FIRE

O Vext inclui um módulo dedicado ao planeamento FIRE, ou seja, Financial Independence, Retire Early.

Este módulo permite explorar:

* valor necessário para atingir independência financeira;
* despesas anuais;
* pressupostos de rentabilidade esperada;
* taxa de levantamento;
* horizonte temporal;
* projeções ajustadas ao impacto fiscal;
* cenários probabilísticos;
* análise de risco e sustentabilidade.

O objetivo é ajudar o utilizador a compreender não apenas a sua situação financeira atual, mas também a sua trajetória de longo prazo.

---

## Visão de Produto

O Vext foi também pensado com potencial de evolução para produto digital.

Possíveis direções futuras incluem:

* plataforma SaaS para investidores individuais;
* relatórios financeiros premium;
* ferramentas fiscais para investidores portugueses;
* versão B2B para contabilistas e consultores financeiros;
* API de cálculos fiscais portugueses;
* integração com corretoras e bancos;
* alertas automáticos de portefólio;
* assistente financeiro com IA.

A visão de longo prazo seria transformar o Vext num sistema operativo financeiro para investidores portugueses.

---

## Objetivo do Repositório

Este repositório tem como objetivo documentar o projeto Vext enquanto protótipo académico e conceito de produto.

Dependendo dos ficheiros disponíveis, o repositório poderá incluir:

* documentação do projeto;
* notas de arquitetura;
* roadmap de desenvolvimento;
* planeamento técnico;
* materiais de apresentação;
* screenshots do protótipo;
* módulos de código selecionados;
* ideias para desenvolvimento futuro.

Dados sensíveis, informação financeira privada, chaves de API e datasets não públicos não devem ser incluídos neste repositório.

---

## Contexto Académico

Este projeto foi desenvolvido no âmbito da unidade curricular de **FinTech**, lecionada pelo Professor **Francisco Pires**.

O projeto permitiu explorar a interseção entre:

* tecnologia financeira;
* inteligência artificial;
* ciência de dados;
* finanças pessoais;
* fiscalidade;
* arquitetura de software;
* desenvolvimento de produto digital.

O desenvolvimento do Vext contribuiu para consolidar conhecimentos em IA aplicada, análise de dados financeiros, desenho modular de sistemas e criação de soluções digitais com potencial de mercado.

---

## Autores

* **Afonso Nunes**
* **Luís Figueira**

Unidade Curricular: **FinTech**

Professor: **Francisco Pires**

---

## Aviso

O Vext é um protótipo académico e não deve ser interpretado como aconselhamento financeiro, fiscal ou de investimento.

Todos os cálculos, pressupostos e resultados devem ser validados de forma independente antes de serem utilizados em decisões financeiras reais.

O projeto tem fins educativos, exploratórios e académicos.

---

## Trabalho Futuro

Possíveis melhorias futuras incluem:

* implementação completa do motor fiscal;
* melhoria do simulador FIRE;
* integração com APIs reais de mercado;
* refinamento do dashboard;
* avaliação do agente de IA;
* geração automática de relatórios;
* aumento da cobertura de testes;
* importação de dados de corretoras;
* templates de apoio ao IRS português;
* estratégia de deployment;
* melhoria da documentação e inclusão de screenshots.

---

## Alunos 

**Afonso Nunes**
Licenciado em Ciência de Dados para a Gestão
Interessado em Inteligência Artificial, Ciência de Dados, FinTech, Agentic AI e desenvolvimento de produtos digitais com IA.

GitHub: [AfonsoNunes03](https://github.com/AfonsoNunes03)
