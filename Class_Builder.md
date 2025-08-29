# Class Builder no ABAP

## O que é?
O **Class Builder** é a ferramenta do SAP utilizada para **criação, edição e manutenção de classes e interfaces** em ABAP.  
Ele é acessado pela **transação SE24**.

O Class Builder é parte do paradigma **ABAP OO (Orientado a Objetos)**, permitindo que você modele soluções utilizando **classes, atributos, métodos e eventos**, organizando melhor a lógica de programação.

---

## Transação
- **SE24** → Criar, visualizar, modificar e testar **classes e interfaces**.  
- **SE80** → Também permite acessar classes dentro dos pacotes.  

---

## Para que serve?
O Class Builder tem como principais funções:
- Criar **classes globais** (disponíveis em todo o sistema).  
- Definir **atributos** (variáveis dentro da classe).  
- Criar **métodos** (funções internas à classe).  
- Implementar **interfaces** (contratos de métodos).  
- Encapsular e organizar a lógica de negócio.  
- Facilitar a reutilização de código.  

---

## Como usar
1. Acesse a transação **SE24**.  
2. Digite o nome da classe (ex.: `ZCL_EXEMPLO_01`).  
3. Clique em **Criar**.  
4. Preencha a descrição e atribua a um pacote.  
5. No menu de definições, configure:  
   - **Atributos** (públicos, protegidos ou privados).  
   - **Métodos** (definição e implementação).  
   - **Eventos** (opcional).  
6. Implemente a lógica na aba **Methods** → **Source Code**.  
7. Ative a classe.  

---

## Exemplo

### Criando uma classe
Nome: `ZCL_CALCULADORA`

**Definição dos métodos:**
- `SOMA` → recebe dois números e retorna o resultado.

**Código no Class Builder (SE24):**

```abap
CLASS zcl_calculadora DEFINITION
  PUBLIC
  FINAL
  CREATE PUBLIC .

  PUBLIC SECTION.
    METHODS:
      soma
        IMPORTING iv_num1 TYPE i
                  iv_num2 TYPE i
        RETURNING VALUE(rv_resultado) TYPE i.
ENDCLASS.


CLASS zcl_calculadora IMPLEMENTATION.
  METHOD soma.
    rv_resultado = iv_num1 + iv_num2.
  ENDMETHOD.
ENDCLASS.

REPORT ztesta_classe.

DATA(lo_calc) = NEW zcl_calculadora( ).
DATA(lv_resultado) = lo_calc->soma( iv_num1 = 10 iv_num2 = 20 ).

WRITE: / 'Resultado da soma:', lv_resultado.

Resultado da soma: 30
