<div align="center">
  <img src="https://raw.githubusercontent.com/MicaelliMedeiros/micaellimedeiros/master/image/computer-ilustra.gif" alt="Coding GIF" width="200"/>
  
  <h1>Olá, eu sou o Jhonata Caetano 👋</h1>
  
  <p>
    <b>Desenvolvedor Full Stack | Analista de Sistemas</b>
  </p>

  <p>
    Transformando problemas complexos em soluções digitais robustas e escaláveis.
  </p>

 <a href="https://www.linkedin.com/in/jhonataclopes/">
  <img src="https://skillicons.dev/icons?i=linkedin" alt="LinkedIn" />
</a>
  <a href="mailto:caetanojhonata@hotmail.com">
     <img src="https://skillicons.dev/icons?i=gmail" alt="Email" />
  </a>
</div>

<hr/>

### 🧐 Sobre mim

Minha missão é crescer como profissional de tecnologia, resolvendo problemas reais de forma estratégica. Tenho background em suporte corporativo e gerenciamento de banco de dados, e hoje atuo diretamente no desenvolvimento de software de ponta a ponta.

- 💼 **Experiência Atual:** Desenvolvedor FullStack Jr na **Álamo Benefícios**, trabalhando com automação, banco de dados (MySQL) e desenvolvimento web.
- 🔭 **Aprimoramento:** Aprofundando em **Arquitetura de Software e Full Stack** na mentoria START do @Luis Dev.
- 🎯 **Foco:** Entregar valor real aos negócios através de código limpo, APIs eficientes, arquiteturas modernas e interfaces premium.

---

### 💼 Experiência Profissional

**Álamo Benefícios**
- 👨‍💻 **Desenvolvedor FullStack Jr** *(Jun 2026 - Presente)*: Desenvolvimento e manutenção de soluções integradas, utilizando banco de dados e automações (MySQL, Google Apps Script).
- 🛠️ **Auxiliar de TI I** *(Dez 2025 - Jun 2026)*: Suporte ao gerenciamento de banco de dados corporativo via sistema SGA, garantindo integridade e disponibilidade de informações.

---

### 🐾 Projeto em Destaque: Lunnar Pet Health (LPH)

> Um ecossistema completo de monitoramento e prontuário inteligente para saúde de pets, desenvolvido com foco em alta manutenibilidade, design premium e práticas robustas de segurança. Este projeto foi construído sob padrões de engenharia de software de nível corporativo e serve como portfólio de referência para aplicações modernas Fullstack (React 19 + NestJS 11 + MySQL).

#### 📸 Visão Geral do Sistema
O **Lunnar Pet Health** permite que tutores e profissionais acompanhem a saúde diária de animais de estimação por meio de um painel de controle interativo. Ele resolve dores reais de monitoramento de rotina através de uma interface baseada em *Glassmorphic design* e uma API REST escalável e segura.

#### ⚡ Principais Funcionalidades

**Front-End (Web)**
* **Dashboard Modular e Personalizável**: Permite ao usuário escolher quais widgets deseja visualizar na tela principal (Calculadora de ração, Diário Fisiológico, Areia, Mimos, Vacinas, Consultas).
* **Calculadora de Consumo de Ração**: Estima automaticamente quantos dias o saco de ração atual durará, alertando o tutor e calculando o custo de alimentação diária por pet.
* **Diário Fisiológico com Regra de Qualidade**: Registro de necessidades com avaliação de qualidade, seguindo as recomendações de consistência veterinária.
* **Gerenciador de Consultas e Linha do Tempo**: Registros médicos com aba sanfonada e suporte a comentários aninhados na consulta.
* **Estilo Ultra Premium & Modo Escuro**: Design elegante baseado em tons quentes e suporte nativo a Tema Escuro com persistência local.

**Back-End (API)**
* **Persistência de Dados Relacional**: Integração completa via **TypeORM** com tabelas estruturadas e chaves estrangeiras com comportamento `CASCADE`.
* **Validação de Entrada Estrita (DTOs)**: Uso de `class-validator` e `class-transformer`. Campos não autorizados nas requisições HTTP são rejeitados antes de atingir o banco.
* **Prevenção contra XSS Armazenado**: Middleware interceptor global que sanitiza tags HTML e injeções de script recursivamente.
* **Segurança de Identificadores (Mitigação de IDOR)**: Uso de UUIDs de alta entropia, inviabilizando ataques de enumeração direta de recursos.

#### 📐 Modelo de Dados (DER Conceitual)

```mermaid
erDiagram
    %% Relacionamento: Um TUTOR possui zero ou muitos PETs
    TUTOR ||--o{ PET : "possui"

    PET {
        uuid id PK
        string name
        string type "enum: dog | cat"
        string breed
        string age
        float bagSizeKg
        int dailyPortionG
        float bagCost "em Reais"
        float remainingKg
        json pottyLogs
        json vaccines
        json consultations
    }

    TUTOR {
        uuid id PK
        string name
    }
