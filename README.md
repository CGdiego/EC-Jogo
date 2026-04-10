<h1 align="center">EC-Jogo</h1>
<p align="center">Projeto de Jogo de Experiência Criativa: Explorando Computação e Inteligência Artificial - PUCPR (2026/1)</p>

---
# Protocolo Sanidade

> *"Você entrou em busca de segurança. O que você vai encontrar é outra coisa."*

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![Plataforma](https://img.shields.io/badge/plataforma-Construct%203-blue)
![Gênero](https://img.shields.io/badge/gênero-Puzzle%20%2F%20Terror%20Psicológico-darkred)

---

## 📖 História

Anos atrás, o governo conduziu um projeto secreto para criar supersoldados por meio de uma droga experimental. Os efeitos colaterais eram devastadores: paranoia, alucinações, agressividade extrema e perda progressiva de memória. O projeto saiu do controle, resultando em mortes e colapsos mentais — e foi então abandonado. A cidade que servia de suporte ao programa seguiu em frente. Os bunkers, enterrados no subsolo, foram esquecidos.

Um dia, um erro em um sistema antigo dispara um **falso alerta de bombardeio**. A população entra em pânico e busca abrigo nos bunkers. O protagonista entra em um deles — que se fecha automaticamente e reinicia protocolos adormecidos há décadas.

Sem saber, ele é **exposto à droga experimental**.

À medida que explora o ambiente, encontra documentos, laboratórios abandonados e vestígios de experimentos fracassados. Sua percepção começa a se fragmentar, misturando **o que é real com o que não é**.

### 🔚 Finais

| Final | Descrição |
|-------|-----------|
| **Final de Dúvida** | O protagonista consegue escapar do bunker, mas as alucinações persistem. A linha entre realidade e delírio permanece turva. |
| **Final de Colapso** | O protagonista perde completamente a sanidade dentro do bunker. Não há saída — nem física, nem mental. |

---

## 🎮 Jogabilidade

**Protocolo Sanidade** é um jogo de **puzzle e terror psicológico** em 2D side-scrolling. O foco está na narrativa imersiva, na exploração cuidadosa do ambiente e na resolução de quebra-cabeças que se tornam progressivamente mais perturbadores.

### ⏱️ Mecânica Central

O jogo é dominado por um **sistema de tempo baseado na exposição à droga**:

- O jogador possui **1 minuto** antes que os efeitos se tornem irreversíveis.
- O tempo impacta diretamente a **narrativa e a dificuldade**.
- Quanto mais o tempo avança, mais intensos se tornam os **efeitos psicológicos visuais e sonoros**.

### 🔍 Desafios e Progressão

O bunker é um labirinto de segredos. Para avançar, o jogador deve:

- Encontrar e decifrar **códigos escondidos**
- Abrir **armários e portas trancadas**
- Coletar e ler **documentos e arquivos**
- Interpretar **textos codificados**
- Usar **cartões de acesso** e lidar com **falhas elétricas**

A dificuldade cresce organicamente com a exploração — o ambiente muda, os efeitos psicológicos aumentam e a fronteira entre real e imaginário se dissolve.

### 🕹️ Controles

| Tecla | Ação |
|-------|------|
| `←` | Mover para a esquerda |
| `→` | Mover para a direita |
| `E` / Clique esquerdo | Interagir com objetos |

### 👻 Inimigo

Uma **sombra paranoica** representa a deterioração mental do protagonista. Ela observa. Surge nas áreas mais escuras. **Não pode ser derrotada — apenas ignorada.**

---

## 🗺️ Fluxograma de Jogo

```mermaid
flowchart TD
    INICIO([Início]) --> ENTRADA[Sala: entrada do bunker]
 
    %% Fluxo da prancheta / definição de usuário
    ENTRADA --> PRANCHETA[Interagir com prancheta]
    PRANCHETA --> INSERIR_NOME[/Inserir nome do usuário/]
    INSERIR_NOME --> SET_USUARIO[Variável usuario = nome]
 
    %% Fluxo da porta do bunker - disponível desde o início
    ENTRADA --> INTERAGIR_PORTA[Interagir com a porta do bunker]
    INTERAGIR_PORTA --> INSERIR_CODIGO[/Inserir código/]
    INSERIR_CODIGO --> CODIGO_CORRETO{Código inserido está correto?}
    CODIGO_CORRETO -- NÃO --> ENTRADA
    CODIGO_CORRETO -- SIM --> CUTSCENE[Ir para Cutscene final]
    CUTSCENE --> FIM([Fim])
 
    %% Fluxo principal - avançar para a direita
    ENTRADA --> ANDAR[Andar até porta da direita]
    SET_USUARIO --> ANDAR
 
    ANDAR --> VAR_USER{Variável usuario está definida?}
    VAR_USER -- NÃO --> ENTRADA
    VAR_USER -- SIM --> SALA_EXP[Passar para sala de experimentos]
 
    %% Sala de experimentos
    SALA_EXP --> COMPUTADOR[Interagir com o computador]
    COMPUTADOR --> TELA_CODIGOS[Tela de códigos de pacientes]
 
    SALA_EXP --> CADEIRA[Interagir com a cadeira]
    CADEIRA --> VISAO[Visão da sala do Laboratório]
 
    %% Dentro da visão do laboratório
    VISAO --> SETA_VOLTAR[Interagir com seta de voltar]
    SETA_VOLTAR --> SALA_EXP
 
    VISAO --> AGUA_OX[Interagir com a água oxigenada]
    AGUA_OX --> SET_AGUA[Setar variável usar da água oxigenada como verdadeira]
    SET_AGUA --> VISAO
 
    VISAO --> ARMARIO[Interagir com armário de vidro]
    ARMARIO --> VAR_USAR{Variável usar da água oxigenada é verdadeira?}
    VAR_USAR -- NÃO --> VISAO
    VAR_USAR -- SIM --> LIMPAR_ARMARIO[Limpar armário de vidro]
    LIMPAR_ARMARIO --> TUBOS[Interagir com tubos de ensaio]
 
    TUBOS --> VAR_AGUA2{Var usar água oxigenada = verdadeiro?}
    VAR_AGUA2 -- NÃO --> VISAO
    VAR_AGUA2 -- SIM --> LIMPAR_TUBOS[Limpar tubos de ensaio]
    LIMPAR_TUBOS --> VISAO
```

---

## 👥 Equipe

| Nome |
|------|
| Carolina Faria Cassaro |
| Diego Fonseca de Oliveira Bonfim Soares |
| Guilherme Ribeiro Rocha |
| Josemar Jorge Correia Filho |

---

## 🛠️ Tecnologias

- **Engine:** [Construct 3](https://www.construct.net/)
- **Estilo:** 2D Side-Scrolling
- **Produção:** Uso de IA assistiva

---

*Protocolo Sanidade — entre antes que o tempo acabe.*
