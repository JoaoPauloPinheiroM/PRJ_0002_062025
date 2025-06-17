# 🚚 Sistema de Gestão de Fretes

![Badge de Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![Badge de Licença](https://img.shields.io/badge/license-MIT-blue)

Um sistema robusto para gerenciar operações de frete, desde o registro inicial até a análise financeira e de desempenho. O objetivo é centralizar informações, automatizar cálculos e fornecer relatórios inteligentes para a tomada de decisão.

## 📋 Índice

- [Sobre o Projeto](#-sobre-o-projeto)
- [Funcionalidades](#-funcionalidades)
- [Casos de Uso](#-casos-de-uso)
- [Tecnologias e Arquitetura](#-tecnologias-e-arquitetura)
- [Plano de Desenvolvimento](#-plano-de-desenvolvimento)
- [Como Contribuir](#-como-contribuir)
- [Licença](#-licença)

---

## 🎯 Sobre o Projeto

Este projeto foi concebido para atender à necessidade de um gerenciamento de fretes eficiente e detalhado. O sistema permite o controle completo de cada operação, incluindo datas importantes, valores financeiros, documentação associada e os envolvidos (motoristas e parceiros).

Além do registro operacional, a plataforma é projetada para ser uma ferramenta de análise, gerando insights valiosos sobre o desempenho dos motoristas, custos e eficiência das rotas.

---

## ✨ Funcionalidades

### 1. Gestão Completa de Fretes
- **Registro de Informações:** Cadastre dados essenciais como número do frete, datas (emissão, carregamento, pagamento, vencimento, finalização), origem, múltiplos destinos e parceiras.
- **Controle Financeiro:** Lance valores detalhados como valor do frete, custo de descarga, valor pago ao motorista e ICMS. O sistema calcula o valor total automaticamente.
- **Associação de Motorista e Veículo:** Vincule facilmente cada operação ao motorista e à placa do veículo responsável.

### 2. Gerenciamento de Documentos
- **Centralização:** Faça o upload de arquivos (PDF) ou insira números/chaves de acesso para documentos importantes como CT-e, NF-e, ARM, RC, PED e Folha de Registro.

### 3. Filtros e Pesquisas Avançadas
- **Busca Detalhada:** A interface permite filtrar fretes por múltiplos critérios:
    - Período (data de emissão, carregamento, pagamento, etc.).
    - Motorista específico.
    - Rota (origem ou destino).
    - Empresa parceira.

### 4. Relatórios e Análises
- **Visão Estratégica:** Gere relatórios essenciais para a gestão do negócio:
    - **Desempenho por Motorista:** Volume de fretes (em quantidade e valor) e tempo médio de transporte.
    - **Status de Operações:** Listagem de fretes pendentes de pagamento ou finalização.
    - **Análise Fiscal:** Total de ICMS pago por período.
    - **Relatório Financeiro Geral:** Consolidado de fretes com totalizadores de valores.
- **Cálculos Automáticos:** O sistema calcula a duração de cada frete e o tempo médio de entrega por motorista.

---

## 🧑‍💻 Casos de Uso

O principal ator do sistema é o **Gestor de Logística**. Abaixo estão os principais casos de uso:

| ID | Nome do Caso de Uso | Descrição Resumida |
| :--- | :--- | :--- |
| **UC-01** | Registrar Novo Frete | O Gestor insere os dados de uma nova operação no sistema. |
| **UC-03** | Lançar Valores Financeiros | O Gestor insere os valores do frete, descarga, motorista e ICMS. |
| **UC-05** | Anexar Documentos | O Gestor anexa ou insere as informações de documentos fiscais e de transporte. |
| **UC-07** | Filtrar Lista de Fretes | O Gestor utiliza filtros (período, motorista, rota) para encontrar operações. |
| **UC-09** | Analisar Desempenho | O Gestor gera relatórios de desempenho dos motoristas. |
| **UC-10** | Consultar Fretes Pendentes | O Gestor lista fretes pendentes de pagamento ou finalização. |
| **UC-12** | Calcular Valor Total | O **Sistema** soma automaticamente o valor do frete e da descarga. |
| **UC-13** | Calcular Duração de Frete | O **Sistema** calcula a duração da operação e o tempo médio por motorista. |

---

## 🛠️ Tecnologias e Arquitetura

A arquitetura do projeto segue uma abordagem moderna e desacoplada, utilizando **.NET** para o backend e **Angular** para o frontend.

### Backend (.NET / C#)
O backend é construído com **ASP.NET Core Web API** e segue os princípios da **Clean Architecture**, promovendo separação de responsabilidades, alta testabilidade e manutenção simplificada.

- **Tecnologias Principais:**
    - **Framework:** .NET 8 (ou superior)
    - **Linguagem:** C#
    - **API:** ASP.NET Core Web API
    - **ORM:** Entity Framework Core
- **Estrutura de Projetos:**
    ```
    /GestaoFretes.sln
    |
    |-- /src
    |   |-- GestaoFretes.Domain      (Entidades e Lógica de Negócio)
    |   |-- GestaoFretes.Application (Serviços e Casos de Uso)
    |   |-- GestaoFretes.Infrastructure (Acesso a Dados, Repositórios)
    |   |-- GestaoFretes.Api         (Controllers da API RESTful)
    |
    |-- /tests
    |   |-- GestaoFretes.Domain.Tests
    |   |-- GestaoFretes.Application.Tests
    ```

### Frontend (Angular / TypeScript)
O frontend é uma **Single Page Application (SPA)** desenvolvida com Angular, garantindo uma experiência de usuário rica e reativa.

- **Tecnologias Principais:**
    - **Framework:** Angular 17 (ou superior)
    - **Linguagem:** TypeScript
    - **Comunicação API:** HttpClient para consumir os endpoints REST do backend.
- **Estrutura de Diretórios:**
    ```
    /gestao-fretes-web
    |-- /src
    |   |-- /app
    |   |   |-- /core (Serviços core, interceptors, guards)
    |   |   |-- /features
    |   |   |   |-- /fretes
    |   |   |   |-- /relatorios
    |   |   |-- /shared (Componentes e pipes compartilhados)
    |   |-- /environments (Configurações de ambiente)
    ```

### Banco de Dados
- **Tecnologia:** Banco de dados relacional.
- **Opções Recomendadas:** **SQL Server**, **PostgreSQL** ou **MySQL**, todos com excelente suporte do Entity Framework Core.

---

## 🚀 Plano de Desenvolvimento

O projeto será desenvolvido em fases para garantir entregas de valor contínuas.

### Fase 1: MVP (Produto Mínimo Viável) - 30 Dias
O foco da primeira fase é entregar todas as funcionalidades essenciais descritas nas seções **Funcionalidades** e **Casos de Uso**. O objetivo é ter um sistema funcional para registro, consulta e geração de relatórios básicos.

### Fase 2: Melhorias Futuras
Após a entrega do MVP, as seguintes funcionalidades serão desenvolvidas:
- **Cadastro Completo de Motoristas:** Módulo dedicado para gerenciar informações detalhadas dos motoristas.
- **Cadastro de Empresas Parceiras:** Um registro completo para gerenciar parceiros e transportadoras.
- **Sistema de Notificações:** Alertas automáticos para eventos importantes (ex: vencimento de frete).
- **Geração de Documentos:** Emissão automática de recibos ou comprovantes de frete.

---

## 🤝 Como Contribuir

Contribuições são o que tornam a comunidade de código aberto um lugar incrível para aprender, inspirar e criar. Qualquer contribuição que você fizer será **muito apreciada**.

1. Faça um *Fork* do projeto
2. Crie uma *Branch* para sua feature (`git checkout -b feature/AmazingFeature`)
3. Faça o *Commit* de suas alterações (`git commit -m 'Add some AmazingFeature'`)
4. Faça o *Push* para a *Branch* (`git push origin feature/AmazingFeature`)
5. Abra um *Pull Request*

---

## 📄 Licença

Distribuído sob a licença MIT. Veja `LICENSE` para mais informações.
