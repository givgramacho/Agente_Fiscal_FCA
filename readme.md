-----

# 🚀 Plataforma de Análise de Notas Fiscais com Agentes de IA

Esta é um agente especializado em Business Intelligence (BI) e Análise de Dados inovadora, que emprega o poder de agentes de Inteligência Artificial para transformar dados brutos de Notas Fiscais (em formato CSV) em dashboards interativos, análises fiscais automáticas e relatórios profissionais em formato `.docx`.

-----

## 🧠 Equipe First Class Agents

Transformamos desafios da sua empresa em soluções inteligentes com o uso de agentes autônomos e análise de dados, facilitando sua tomada de decisão no que realmente importa para o seu negócio.

-----

## Como Executar o Projeto

Siga os passos abaixo para configurar e executar a aplicação:

### 1\. Clonar ou Baixar o Projeto

Primeiro, clone ou baixe os arquivos do projeto para uma pasta no seu computador. Você pode fazer isso de duas maneiras:

  * **Baixar como ZIP:** Vá no botão verde "Code" no GitHub e selecione "Download ZIP".
  * **Via Terminal:** Use o comando `git clone` no seu terminal:
    ```bash
    git clone https://github.com/asegnini/I2A2.git
    ```

### 2\. Criar um Ambiente Virtual

Abra um terminal na pasta do projeto e execute o seguinte comando:

```bash
python -m venv .venv
```

### 3\. Ativar o Ambiente Virtual

#### No Windows

```bash
.\.venv\Scripts\activate
```

#### No macOS/Linux

```bash
source .venv/bin/activate
```

### 4\. Instalar as Dependências

Com o ambiente virtual ativado, execute o comando abaixo para instalar todas as bibliotecas listadas no `requirements.txt`:

```bash
pip install -r requirements.txt
```

### 5\. Configurar a Chave de API

Para que a aplicação funcione corretamente, você precisa configurar sua chave de API do Google Gemini:

1.  Crie uma pasta chamada **`.streamlit`** na raiz do seu projeto.

2.  Dentro dela, crie um arquivo chamado **`secrets.toml`**.

3.  Adicione sua chave de API do Google Gemini ao arquivo da seguinte forma, substituindo `"SUA_CHAVE_DE_API_VAI_AQUI"` pela sua chave real:

    ```toml
    GOOGLE_API_KEY = "SUA_CHAVE_DE_API_VAI_AQUI"
    ```

### 6\. Executar a Aplicação

Com todas as configurações feitas e o ambiente virtual ativado, execute a aplicação Streamlit:

```bash
streamlit run app.py
```

Isso abrirá a aplicação no seu navegador padrão.

-----

## ✨ Funcionalidades Principais

A aplicação é organizada em cinco abas principais, cada uma projetada com um propósito claro para otimizar sua análise fiscal:

### 💬 Agente Q\&A

Uma interface de chat intuitiva que permite fazer perguntas específicas em linguagem natural diretamente ao conjunto de dados. Ideal para investigações pontuais e obtenção rápida de informações.

### 💡 Insights da IA

Ferramenta de "um clique" que instrui o agente a responder a 10 perguntas de negócio fundamentais. Gera um relatório de insights automáticos que pode ser facilmente adicionado ao documento final.

### 📊 Dashboard

Um painel de controle visual e interativo que oferece uma visão abrangente dos seus dados:

  * **Mapeamento de Colunas:** Permite ao usuário mapear as colunas do seu arquivo para conceitos de negócio essenciais (Cliente, Produto, Quantidade), garantindo a adaptabilidade da ferramenta a diversas fontes de dados.
  * **KPIs Dinâmicos:** Exibe os principais indicadores de performance (Faturamento Total, Itens Vendidos, etc.).
  * **Gráficos Curados:** Apresenta análises visuais automáticas dos Top 10 Clientes, Top 10 Produtos e Vendas ao Longo do Tempo.

### ✅ Análise Fiscal

Um painel dedicado à auditoria fiscal, que executa análises cruciais baseadas nas colunas disponíveis no arquivo. Inclui verificações de consistência de valores e análise detalhada de operações por CFOP.

### 📄 Montador de Relatório

Área de preparação para o relatório final:

  * **Preview Interativo:** Exibe todos os itens "pinados" (gráficos, tabelas, insights) para revisão.
  * **Gerenciamento:** Permite remover itens individualmente antes da exportação.
  * **Exportação Profissional:** Gera um documento `.docx` de alta qualidade, com capa, títulos e gráficos renderizados como imagens nítidas.

-----

## 🛠️ Stack de Tecnologias

  * **Linguagem:** Python 3.11+
  * **Framework Web/UI:** Streamlit
  * **Análise de Dados:** Pandas
  * **Inteligência Artificial (LLM):** Google Gemini Pro / Flash
  * **Orquestração de Agentes:** LangChain, LangChain Experimental
  * **Visualização de Dados:** Plotly Express
  * **Geração de Documentos:** `python-docx`
  * **Exportação de Gráficos:** `Kaleido`
  * **Mecanismo de Retry:** `Tenacity`

-----

## 📂 Estrutura do Projeto

```bash
/
├── .streamlit/
│   └── secrets.toml        # Armazena as chaves de API
│
├── tabs/
│   ├── __init__.py
│   ├── agent_tab.py        # Aba de Q&A manual
│   ├── insights_tab.py     # Aba de Insights Automáticos da IA
│   ├── dashboard_tab.py    # Aba do painel de controle visual
│   ├── fiscal_tab.py       # Aba de Análise Fiscal
│   └── report_tab.py       # Aba do montador de relatório
│
├── utils/
│   ├── __init__.py
│   ├── callbacks.py        # Logger customizado para o terminal
│   └── processing.py       # Funções de processamento e geração do .docx
│
├── app.py                  # Ponto de entrada da aplicação
├── requirements.txt        # Lista de dependências
└── README.md               # Esta documentação
```
