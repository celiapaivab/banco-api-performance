# Testre de Performance do Banco API com K6

Este repositório contém testes de performance desenvolvidos com **JavaScript** e **K6**, aplicados aos endpoints da API do projeto **Banco**.

Repositório: [Banco API Performance](https://github.com/celiapaivab/banco-api-performance)

## Objetivo

Este projeto tem como obejtivo simular diferentes cargas e cenários de uso para a API do banco, avaliando seu desempenho e identificando possíveis gargalos. Os testes são escritos com foco em modularidade, organização por contexto e reutilização de modelos de dados.

---

## Tecnologias Utilizadas

- **[K6](https://k6.io/)** → ferramenta de testes de performance.
- **JavaScript (ES6+)** → linguagem utilizada para criação dos cenários.
- **Node.js & npm** → gerenciamento de dependências e execução de scripts auxiliares.

---

## Estrutura do Repositório

```
banco-api-performance/
│── config/
│── fixtures/
│── helpers/
│── tests/
│   ├── login.test.js
│   ├── transferencias.test.js
│── utils/
│── .gitignore
│── README.md
```

---

## Objetivo de Cada Grupo de Arquivos

- **config/** → arquivos de configuração de variáveis de ambiente.
- **fixtures/** → dados de entrada para os testes.
- **helpers/** → funções auxiliares para autenticação e suporte aos testes.
- **tests/** → conjunto de testes de performance po módulo da API.
- **utils/** → módulos utilitários reutilizáveis para interação e manipulação de dados da API.

---

## Instalação e Execução

1. Clone este repositório:

```bash
git clone https://github.com/celiapaivab/banco-api-performance.git
cd banco-api-performance
```

2. Altere o arquvio `config/config.local.json` e defina a URL da sua API.

```json
{
  "baseUrl": "http://localhost:3000"
}
```

3. Execute o teste

```bash
k6 run tests/login.test.js
```

Certifique-se de passar a variável de ambiente
`BASE_URL`, caso não esteja usando um `config/config.local.json` ou uma abordagem de carregamento automático:

```bash
k6 run tests/login.test.js -e BASE_URL=http://localhost:3000
```

4. Acompanhamento em tempo real via dashboard do K6

```bash
K6_WEB_DASHBOARD=true k6 run tests/login.test.js
```

5. Exportação de relatório HTML após execução

```bash
K6_WEB_DASHBOARD=true K6_WEB_DASHBOARD_EXPORT=html-report.html k6 run tests/login.test.js
```

O relatório será gerado no arquivo `html-report.html`.

---
