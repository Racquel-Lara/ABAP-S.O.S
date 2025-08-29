# Conceitos Fundamentais de SAP ABAP

Este documento reúne os principais **conceitos introdutórios de SAP ABAP**.  
O objetivo é servir como um guia de referência rápida para desenvolvedores, consultores e estudantes que estão iniciando no mundo SAP.

---

## 🔑 Transações
- **Transação** é um atalho que leva o usuário diretamente a uma funcionalidade no SAP GUI ou Fiori.
- Exemplos:
  - `SE80`: Object Navigator (programas, classes, funções, pacotes etc.)
  - `SE11`: Dicionário ABAP (tabelas, views, estruturas, domínios)
  - `SE38`: Criar e executar programas
  - `SE93`: Criar ou visualizar transações
- As transações podem ser técnicas (para desenvolvimento) ou de negócio (para operações no ERP).

---

## 🖥️ Ambientes SAP (Landscape)
Normalmente, um sistema SAP é dividido em **três ambientes principais**:
- **DEV (Development):** onde os objetos são criados, testados de forma unitária e versionados.
- **QA (Quality Assurance/Test):** onde os objetos são testados em conjunto (integração) por consultores e key users.
- **PRD (Production):** ambiente produtivo, utilizado pelos usuários finais, onde não se pode desenvolver diretamente.

Esse ciclo garante controle de qualidade e segurança antes que uma alteração chegue ao ambiente produtivo.

---

## 📦 Pacotes
- **Pacote** (antigamente chamado de *development class*) é a unidade organizacional onde os objetos ABAP ficam armazenados.
- Serve para agrupar programas, classes, tabelas e outros artefatos de acordo com o módulo ou projeto.
- Pacotes podem ser **transportáveis** (migrar via requests para QA e PRD) ou **locais** (uso apenas em DEV, não transportáveis).

---

## 🚚 Transport Organizer (Requests & Tasks)
O **sistema de transporte** garante que os objetos desenvolvidos em DEV cheguem até PRD com segurança.  
No SAP, esse controle é feito via **Transport Organizer**:

- **Request (Ordem de Transporte):**
  - Unidade principal de transporte.
  - Pode conter uma ou várias *tasks*.
  - Identificada por número único (ex.: `DEVK900123`).

- **Task:**
  - Subdivisão de uma request, geralmente associada a um desenvolvedor.
  - Quando concluída, precisa ser liberada para que a *request* possa ser liberada também.

- Fluxo típico:
  1. Criar/alterar objeto em DEV → ele é atribuído a uma **task**.
  2. Desenvolvedor libera sua task.
  3. Consultor libera a **request**.
  4. A request é transportada para QA e, após testes, para PRD.

---

## 📑 Outros Conceitos Importantes
- **Cliente (Mandante):** cada ambiente SAP pode ter múltiplos clientes (ex.: `100`, `200`, `300`), usados para separar dados e cenários.
- **Workbench vs. Customizing:**
  - *Workbench*: objetos técnicos (programas, tabelas, classes, pacotes).
  - *Customizing*: configurações de negócio (parametrizações feitas via transações como `SPRO`).
- **Autorizações:** controlam o que cada usuário pode visualizar ou executar no sistema.
- **Naming Convention:** em projetos, geralmente objetos Z* ou Y* são usados para desenvolvimentos customizados.

---

## 🎯 Resumo
- **Transações**: atalhos para funções no SAP.  
- **Ambientes**: DEV → QA → PRD, garantindo qualidade e segurança.  
- **Pacotes**: agrupam objetos ABAP para transporte e organização.  
- **Requests & Tasks**: controlam o ciclo de transporte dos objetos.  
- **Conceitos extras**: clientes, workbench/customizing, autorizações e convenções de nomenclatura.  

---

📌 Este arquivo pode ser expandido futuramente com exemplos práticos, boas práticas e fluxos comuns em projetos SAP ABAP.
