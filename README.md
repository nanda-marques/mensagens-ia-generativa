# Mensagens com IA Generativa

Projeto desenvolvido em Python que gera dados fictícios de clientes bancários, expõe esses dados via API REST local e utiliza IA generativa para criar mensagens personalizadas de marketing financeiro para cada usuário.

---

## Sobre o Projeto

O sistema realiza as seguintes etapas:

1. Gera 500 clientes fictícios com dados bancários em formato JSON
2. Converte os dados para CSV organizado com pandas
3. Sobe uma API REST local com FastAPI para consultar e atualizar os dados
4. Consome a API com a biblioteca `requests`
5. Usa IA generativa (via OpenRouter) para gerar mensagens personalizadas no campo `news` de cada usuário

---

## Bibliotecas Utilizadas

Instale todas as dependências com:

```bash
pip install fastapi uvicorn pandas requests openai
```

| Biblioteca | Uso |
|---|---|
| `pandas` | Leitura, manipulação e exportação do CSV |
| `fastapi` | Criação da API REST local |
| `uvicorn` | Servidor ASGI para rodar o FastAPI |
| `requests` | Consumo da API dentro do notebook |
| `openai` | Integração com modelos de IA via OpenRouter |
| `json` | Manipulação de dados JSON |

---

## Como Rodar a API Localmente

### Clone o repositório

```bash
git clone https://github.com/nanda-marques/mensagens-ia-generativa.git
cd mensagens-ia-generativa
```

### Instale as dependências

```bash
pip install fastapi uvicorn pandas requests openai
```

### Suba o servidor

```bash
uvicorn api:app --reload
```

### Acesse as rotas

| Rota | Método | Descrição |
|---|---|---|
| `http://127.0.0.1:8000/` | GET | Verifica se a API está no ar |
| `http://127.0.0.1:8000/users` | GET | Lista todos os usuários |
| `http://127.0.0.1:8000/users/{id}` | GET | Busca usuário por ID |
| `http://127.0.0.1:8000/users/{id}` | PUT | Atualiza dados do usuário |
| `http://127.0.0.1:8000/docs` | GET | Documentação interativa automática |

---

## Integrando IA Generativa (OpenRouter)

O projeto usa o **OpenRouter** para acessar modelos de IA gratuitamente.

### Como obter sua chave de API gratuita

1. Acesse **[openrouter.ai](https://openrouter.ai)**
2. Crie uma conta ou faça login
3. Vá em **Keys → Create Key**
4. Copie a chave gerada (começa com `sk-or-v1-...`)

### Como usar no projeto

Crie um arquivo `.env` na raiz do projeto:

```
OPENROUTER_API_KEY=sk-or-v1-SUA_CHAVE_AQUI
```
