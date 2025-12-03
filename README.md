# DimenDevour

> **Desenvolvimento de uma Visual Novel híbrida com sistema de combate rítmico e narrativa ramificada.**

---

## Informações do Projeto

| Campo | Detalhe |
| :--- | :--- |
| **Estudante** | Gustavo do Prado Lima |
| **Curso** | Engenharia de Software |
| **Data de Entrega** | 02/12/2025 |
| **Engine** | Godot 4+ |
| **Linguagem** | GDScript |

---

## Resumo

Este trabalho compõe a proposta de portfólio **“DimenDevour”**, um jogo híbrido que une a narrativa densa de uma Visual Novel com a intensidade de mecânicas de jogos de ritmo. A trama acompanha Bill, um jovem que, após uma tragédia causada por criaturas transdimensionais conhecidas como "Devoradores", busca uma forma de voltar no tempo e salvar aqueles que ama.

O projeto tem como objetivo central o desenvolvimento de uma arquitetura de software capaz de alternar fluidamente entre dois modos de jogo distintos: a exploração narrativa (baseada em máquinas de estados e diálogos ramificados) e o combate rítmico (que exige sincronia precisa de *inputs* e processamento de áudio em tempo real).

O jogo é estruturado em capítulos, sendo o escopo deste portfólio o **Primeiro Ato** (apresentação do mundo, o incidente incitante na Ilha de Fera e a fuga). O resultado esperado é um protótipo vertical funcional onde as escolhas narrativas influenciam o contexto das batalhas e o desempenho rítmico do jogador dita o sucesso ou fracasso da jornada.

---

## 1. Introdução

### Contexto
O mercado de jogos independentes tem se destacado pela fusão de gêneros. Enquanto Visual Novels tradicionais focam quase exclusivamente na leitura, e jogos de ritmo focam apenas na mecânica, **DimenDevour** propõe uma intersecção onde a narrativa dita o ritmo da batalha. O uso de **Máquinas de Estados Finitos (FSM)** para gerenciar a complexidade da trama, aliado a algoritmos de sincronia de áudio (*Audio Server*), permite uma experiência imersiva onde a música reflete a tensão narrativa.

### Objetivos
* **Objetivo Principal:** Desenvolver um protótipo funcional do primeiro ato de "DimenDevour", integrando narrativa visual e combate rítmico.
* **Objetivos Secundários:**
    * Implementar um sistema de diálogo robusto com suporte a sprites dinâmicos (expressões faciais).
    * Criar um sistema de batalha rítmica ("Conductor System") que processe inputs com base em BPM (Batidas Por Minuto).

---

## 2. Descrição do Projeto

* **Linha de Projeto:** Jogos Digitais.
* **Tema:** Visual Novel de Horror/Mistério com Batalhas de Ritmo.
* **Propósito:** Oferecer uma narrativa divertida que engaje o jogador através de desafios de habilidade motora (ritmo).
* **Público-Alvo:** Jovens adultos fãs de narrativas interativas, jogos de ritmo e histórias de mistério/horror e comédia.

### Problemas a Resolver
* Falta de interatividade mecânica em Visual Novels tradicionais.
* Dificuldade técnica em sincronizar animações e inputs com trilhas sonoras dinâmicas na Godot Engine.

### Diferenciação/Ineditismo
O projeto se destaca pela **identidade cultural** (protagonistas e folclore com inspiração brasileira) e pela **tonalidade única**, misturando tragédia pesada com humor absurdo e horror cósmico.

### Limitações
* O protótipo cobrirá apenas o **Primeiro Ato** (6 capítulos).
* O sistema de ritmo será focado em *inputs* de teclado (PC), sem suporte inicial a controles dedicados ou mobile.

### Métricas de Sucesso
* Sincronia precisa entre o áudio e a detecção de *hit* (input do jogador).
* Fluidez na transição entre modo novela (diálogo) e modo batalha.
* Clareza da interface (HUD) durante as cenas de ritmo caóticas.

---

## 3. Especificação Técnica

### 3.1. Requisitos de Software

#### Requisitos Funcionais (RF)
- [x] **RF01 - Sistema de Diálogo:** O jogo deve carregar scripts de texto, exibir falas caractere por caractere e alterar os sprites dos personagens (expressões) conforme tags no texto.
- [x] **RF02 - Batalha Rítmica:** O sistema deve gerar "notas" visuais sincronizadas com o BPM da música; o jogador deve pressionar teclas no momento exato para causar dano.
- [x] **RF03 - Sistema de Quest/Progresso:** O jogo deve rastrear o estado da narrativa (flags) para saber quais eventos já ocorreram (ex: "Vitoria resgatada").
- [x] **RF04 - Interface (HUD):** Exibir barra de vida, pontuação de combo e feedback visual de acerto/erro (Perfect/Miss).
- [x] **RF05 - Save/Load:** Persistência de dados locais para salvar o capítulo atual.

#### Requisitos Não-Funcionais (RNF)
- [ ] **RNF01 - Desempenho:** O sistema de ritmo não deve ter latência perceptível (input lag < 15ms).
- [ ] **RNF02 - Estética:** Arte híbrida e consistente..
- [ ] **RNF03 - Portabilidade:** Executável para Windows.
- [ ] **RNF04 - Usabilidade:** Mapeamento de teclas intuitivo e feedback sonoro claro.

### 3.2. Considerações de Design

* **Padrões de Arquitetura:**
    * **State Pattern:** Para gerenciar os estados do jogo (Menu, Roam, Dialogue, Battle).
    * **Observer Pattern:** Para o sistema de eventos (ex: quando a música atinge a batida X, gera o inimigo Y).
* **Decisões:** Uso da **Godot Engine** pela facilidade de manipulação de nós 2D e excelente sistema de áudio. Arte criada no **Aseprite** (pixel art) e **Krita** (ilustrações HD) para garantir identidade visual única.

### 3.3. Stack Tecnológica

* **Linguagens:** GDScript.
* **Frameworks/Bibliotecas:** Godot Engine 4.x.
* **Ferramentas de Gestão:** Trello (Kanban), Git/GitHub (Versionamento).
* **Ferramentas de Arte:** Aseprite (Sprites/Tilesets), Krita (Character Design/CGs).

### 3.4. Considerações de Segurança e Ética
* **Licenciamento:** Todo código autoral sob licença MIT. Assets visuais sob Creative Commons.
* **Ética:** O enredo trata de temas sensíveis (luto, perda, violência psicológica). Haverá avisos de gatilho (Trigger Warnings) no início da execução. Não há coleta de dados de usuários.

---

## 4. Próximos Passos

### 4.1. Etapas Planejadas

O projeto "DimenDevour" segue um cronograma de desenvolvimento iterativo:

1.  **Pré-Produção (Atual):** Finalização do roteiro do Ato 1 e Concept Art dos personagens principais.
2.  **Prototipagem Mecânica:** Implementação do "Conductor" (controlador de ritmo) na Godot.
3.  **Integração:** Unir o sistema de diálogo com o sistema de batalha.
4.  **Produção de Assets:** Criação dos cenários da Ilha de Fera e sprites finais.
5.  **Polimento:** Efeitos visuais (VFX), balanceamento da dificuldade rítmica e testes de usuário.

### 4.2. Marcos e Checkpoints

| Marco | Descrição | Previsão |
| :--- | :--- | :--- |
| **M1** | Roteiro do Ato 1 Completo e Design Doc | Outubro / 2025 |
| **M2** | Desenvolvimento de assets | Fevereiro / 2026 |
| **M2** | Sistema de Diálogo + Movimentação (Pixel Art) | Março / 2026 |
| **M3** | Sistema de Batalha Rítmica Funcional (MVP) | Abril / 2026 |
| **M4** | Integração da Narrativa com Batalha (Alpha) | Maio / 2026 |
| **M5** | Versão Final do Portfólio (Ato 1) | Junho / 2026 |

---

## 5. Referências

1.  **GODOT ENGINE DOCUMENTATION.** AudioStreamPlayer and Syncing. Disponível em: docs.godotengine.org.
2.  **SCHWAB, Brian.** *AI Game Engine Programming*. (Referência para máquinas de estados).
3.  **LEBIGOT, T.** *Rhythm Game Programming Patterns in Godot*.
4.  **BRASIL.** Lei n. 9.610, de 19 de fevereiro de 1998 (Direitos Autorais).

---
*Este projeto é desenvolvido para fins acadêmicos no curso de Engenharia de Software.*
