# Function Builder no ABAP

## O que é?
O **Function Builder** é a ferramenta do SAP utilizada para **criação, edição e gerenciamento de Módulos de Função** (*Function Modules*).  
Ele é acessado principalmente através da **transação SE37**.

Módulos de função são blocos de código reutilizáveis que encapsulam uma lógica específica e podem ser chamados de qualquer parte do sistema, inclusive por **outros programas ABAP, classes, relatórios ou até sistemas externos** (via RFC).

---

## Transação
- **SE37** → Criar, visualizar, modificar e testar módulos de função individualmente.  
- **SE80** → Também permite acessar módulos de função dentro de *Function Groups*.  

---

## Para que serve?
O Function Builder tem como principais funções:
- Criar **módulos de função reutilizáveis**;
- Definir **parâmetros de importação e exportação** (entradas e saídas);
- Definir **tabelas internas** e **exceções**;
- Testar módulos de forma isolada antes de usá-los em programas reais;
- Agrupar funções relacionadas em **Function Groups**.

> 💡 Um Function Module sempre pertence a um **Function Group**. O *Group* fornece o contexto global (como variáveis globais compartilhadas entre os módulos do grupo).

---

## Como usar
1. Acesse a transação **SE37**.  
2. Digite o nome do módulo de função (ex.: `ZFM_EXEMPLO_01`).  
3. Clique em **Criar**.  
4. Escolha ou crie um **Function Group** (ex.: `ZFG_EXEMPLO`).  
5. Defina:
   - **Import parameters** (entradas);
   - **Export parameters** (saídas);
   - **Changing parameters** (entradas/saídas);
   - **Tables** (opcional, geralmente substituídas por *internal tables* nos parâmetros);
   - **Exceptions** (tratamento de erros).  
6. Escreva a lógica ABAP na aba **Source Code**.  
7. Ative o módulo de função e teste.

---

## Exemplo

### Criando um módulo de função
Nome: `ZFM_SOMA_NUMEROS`  
Function Group: `ZFG_EXEMPLOS`

**Definição dos parâmetros:**
- Import:  
  - `IV_NUM1` (TYPE I)  
  - `IV_NUM2` (TYPE I)  
- Export:  
  - `EV_RESULTADO` (TYPE I)

**Código no Function Builder:**
```abap
FUNCTION zfm_soma_numeros.
*"----------------------------------------------------------------------
*"*"Interface local:
*"  IMPORTING
*"     VALUE(iv_num1) TYPE i
*"     VALUE(iv_num2) TYPE i
*"  EXPORTING
*"     VALUE(ev_resultado) TYPE i
*"----------------------------------------------------------------------
  ev_resultado = iv_num1 + iv_num2.
ENDFUNCTION.

REPORT ztesta_funcao.

DATA: lv_resultado TYPE i.

CALL FUNCTION 'ZFM_SOMA_NUMEROS'
  EXPORTING
    iv_num1      = 5
    iv_num2      = 7
  IMPORTING
    ev_resultado = lv_resultado.

WRITE: / 'Resultado da soma:', lv_resultado.

Resultado da soma: 12

