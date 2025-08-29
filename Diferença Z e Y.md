# Utilização da Nomenclatura Z e Y em ABAP

No universo de desenvolvimento ABAP para SAP, a utilização de uma nomenclatura consistente é crucial para a organização, manutenção e transporte de objetos.  
Dentre as convenções mais importantes está a que dita o uso dos prefixos **Z** e **Y** para objetos customizados.  
Este documento visa esclarecer a diferença fundamental entre eles, com foco na **transportabilidade** dos desenvolvimentos.

---

## O Namespace do Cliente: Z e Y
A SAP reserva para si todos os objetos iniciados com letras de **A a X**.  
Para garantir que os desenvolvimentos realizados pelos clientes não entrem em conflito com os objetos *standard* do sistema, a SAP disponibilizou os **namespaces iniciados com as letras Z e Y**.  

Qualquer programa, tabela, função ou outro objeto que você criar no ambiente de desenvolvimento ABAP deve, por padrão, começar com uma dessas duas letras.

---

## A Principal Diferença: Transportabilidade
Embora seja tecnicamente possível configurar o sistema de outras formas, a convenção mais difundida e adotada na comunidade ABAP globalmente é a seguinte:

### 🔹 Nomenclatura **Z**
Objetos iniciados com **Z** são destinados a desenvolvimentos que serão **transportados** através da sua *landscape* de sistemas, ou seja, que sairão do ambiente de **desenvolvimento (DEV)** para **qualidade (QAS)** e, posteriormente, para **produção (PRD)**.

- **Uso comum:** programas, relatórios, tabelas de banco de dados, classes, módulos de função e qualquer outro objeto que precise ser utilizado em produção.  
- **Transporte:** ao criar ou modificar um objeto **Z**, o sistema SAP solicitará a criação ou inclusão em uma **Transport Request (Ordem de Transporte)**.  
- **Exemplo:** `ZRELC_VENDAS_001` (um relatório de vendas customizado).

---

### 🔹 Nomenclatura **Y**
Objetos iniciados com **Y** são, por convenção, utilizados para **desenvolvimentos locais, testes ou objetos que não devem ser transportados**.

- **Uso comum:** programas de teste para um desenvolvedor específico, objetos temporários para análise ou desenvolvimentos relevantes apenas em DEV.  
- **Transporte:** geralmente salvos no pacote **$TMP**. Neste caso, o sistema **não solicitará** uma Transport Request.  
- **Exemplo:** `YTESTE_MARCELO_01` (um programa de teste pessoal).

---

## Por que seguir esta convenção?

Adotar a distinção entre **Z** e **Y** traz diversos benefícios:

- **Clareza:** fica claro para a equipe a finalidade de um objeto.  
- **Organização:** facilita identificar e descartar objetos que não são mais necessários.  
- **Segurança:** reduz o risco de transportar objetos incompletos ou de teste para produção.

---

## Outras Interpretações (Menos Comuns)

Embora a distinção de transportabilidade seja a mais comum, em algumas empresas você pode encontrar outras interpretações:

- **Z para desenvolvimentos "do zero"** e **Y para cópias de objetos standard**.  
- **Z para desenvolvimento local** e **Y para desenvolvimento central** em grandes corporações.

> ⚠️ No entanto, a prática mais recomendada e atual é focar na **transportabilidade**.

---

## Conclusão
Para o seu repositório **abap-s.o.s**, a recomendação é clara:  
- Utilize **Z** para todo desenvolvimento que precise ser transportado e usado em produção.  
- Reserve **Y** para objetos locais, de teste e não transportáveis, associando-os ao pacote **$TMP**.  

Essa prática garantirá um ciclo de vida de desenvolvimento **mais seguro, organizado e eficiente**.
