# Introdução ao ABAP e RICEFW

## O que é ABAP?

**ABAP (Advanced Business Application Programming)** é a linguagem de programação proprietária da **SAP**, criada para o desenvolvimento de aplicações de negócios dentro do **SAP ERP** e de outras soluções da empresa. Inicialmente utilizada para relatórios e customizações em sistemas SAP clássicos (SAP ECC), o ABAP evoluiu para suportar tanto a programação procedural quanto orientada a objetos, além de recursos modernos como **CDS Views** e o modelo **RAP**. Ele é a base para praticamente todas as customizações, relatórios, integrações e extensões dentro do ecossistema SAP, sendo essencial para empresas que utilizam os sistemas da companhia.

## O que é RICEFW?

No contexto SAP, existe o conceito de **RICEFW**, um acrônimo que categoriza os principais tipos de objetos desenvolvidos em projetos:

* **R**eports (Relatórios)
* **I**nterfaces (Integrações entre sistemas)
* **C**onversions (Conversões de dados)
* **E**nhancements (Melhorias/Extensões)
* **F**orms (Formulários)
* **W**orkflows (Fluxos de trabalho)

Esses elementos representam as principais demandas de desenvolvimento ABAP em implementações e manutenções de sistemas. Em resumo, o ABAP é a linguagem que permite criar e adaptar soluções dentro do SAP, enquanto o RICEFW funciona como um guia para organizar e estruturar esses desenvolvimentos no ciclo de vida dos projetos.

# Tecnologias Modernas ABAP

## Core Data Services (CDS)

Os **CDS (Core Data Services)** são a forma moderna de modelar dados no SAP. Eles permitem criar **views semânticas** diretamente no banco de dados, com anotações que enriquecem as entidades (como textos descritivos, associações e cálculos). Os CDS substituem a lógica de relatórios pesados em ABAP clássico, trazendo consultas otimizadas, reutilizáveis e com integração nativa ao **SAP Fiori** e ao **RAP**.

## RESTful ABAP Programming Model (RAP)

O **RAP (RESTful ABAP Programming Model)** é o modelo de programação mais recente para desenvolvimento de aplicações no **SAP S/4HANA**. Ele combina CDS, definições de comportamento (Behavior Definitions) e serviços OData para entregar aplicações modernas baseadas em **SAP Fiori**. O RAP pode ser utilizado em dois cenários: **Managed**, em que o framework gerencia persistência e operações padrão, e **Unmanaged**, quando é necessário maior controle pelo desenvolvedor.

## SAP Business Technology Platform (BTP)

A **SAP BTP (Business Technology Platform)** é a plataforma em nuvem da SAP que integra dados, inteligência artificial, analytics e extensões de aplicações. No contexto do ABAP, a BTP oferece o **ABAP Environment (Steampunk)**, que permite desenvolver extensões em ABAP diretamente na nuvem, de forma desacoplada do sistema central (S/4HANA). Assim, empresas podem inovar e estender suas soluções sem modificar o núcleo padrão do SAP.
