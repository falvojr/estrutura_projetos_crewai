# Estrutura de Projetos CrewAI

Sistema multi-agente de IA para pesquisa e criação de relatórios, desenvolvido com [crewAI](https://crewai.com).

## Estrutura do Projeto

```
estrutura_projetos_crewai/
├── .env                           # Variáveis de ambiente (modelo LLM)
├── .gitignore                     # Arquivos ignorados pelo Git
├── README.md                      # Documentação do projeto
├── pyproject.toml                 # Configurações e dependências do projeto
├── knowledge/                     # Base de conhecimento
│   └── user_preference.txt        # Preferências do usuário
└── src/estrutura_projetos_crewai/
    ├── __init__.py               # Inicialização do pacote
    ├── main.py                   # Ponto de entrada principal
    ├── crew.py                   # Definição da equipe de agentes
    ├── config/                   # Configurações dos agentes e tarefas
    │   ├── agents.yaml           # Configuração dos agentes
    │   └── tasks.yaml            # Configuração das tarefas
    └── tools/                    # Ferramentas customizadas
        ├── __init__.py
        └── custom_tool.py        # Exemplo de ferramenta personalizada
```

## Principais Arquivos

### **config/agents.yaml**
Define os agentes da equipe:
- **researcher**: Pesquisador sênior especializado em encontrar avanços inovadores
- **reporting_analyst**: Analista que transforma dados em relatórios detalhados

### **config/tasks.yaml**
Define as tarefas executadas pelos agentes:
- **research_task**: Conduz pesquisa aprofundada sobre um tópico
- **reporting_task**: Cria relatório completo em markdown

### **crew.py**
Orquestra os agentes e tarefas, configurando o fluxo de trabalho sequencial.

### **main.py**
Ponto de entrada com funções para executar, treinar e testar a equipe.

## Instalação

Certifique-se de ter Python >=3.10 <3.13 instalado.

### 1. Criar o projeto
```bash
crewai create crew estrutura_projetos_crewai
```

### 2. Instalar dependências
```bash
crewai install
```

### 3. Configurar variáveis de ambiente
Adicione sua chave de API no arquivo `.env`, no nosso caso estamos usando um LLM localmente:
```bash
MODEL=ollama/llama3.1
API_BASE=http://localhost:11434
```

## Execução

Para executar a equipe de agentes:

```bash
crewai run
```

Este comando irá:
1. Inicializar os agentes configurados
2. Executar a pesquisa sobre o tópico definido
3. Gerar um relatório completo em `report.md`

## Personalização

- **Agentes**: Modifique `config/agents.yaml` para definir novos agentes
- **Tarefas**: Edite `config/tasks.yaml` para criar novas tarefas
- **Lógica**: Customize `crew.py` para adicionar ferramentas e argumentos específicos
- **Entrada**: Altere `main.py` para definir novos inputs para agentes e tarefas

## Requisitos

- Python >=3.10 <3.13
- CrewAI framework
- Chave de API OpenAI (ou outro provedor LLM configurado)

## Suporte

- [Documentação CrewAI](https://docs.crewai.com)
- [Repositório GitHub](https://github.com/joaomdmoura/crewai)
- [Discord](https://discord.com/invite/X4JWnZnxPb)