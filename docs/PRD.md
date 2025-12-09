# Documentação de Requisitos do Produto (PRD) - Aquarius

## 1. Visão Geral
O **Aquarius** é uma aplicação completa (Full Stack) projetada para monitorar e acompanhar a atividade parlamentar brasileira. O objetivo é fornecer aos cidadãos uma ferramenta acessível e inteligente para fiscalizar e entender o trabalho dos seus representantes na Câmara dos Deputados e no Senado Federal.

## 2. Público-Alvo
- Cidadãos brasileiros interessados em política.
- Jornalistas e pesquisadores.
- Organizações não governamentais (ONGs) de fiscalização.

## 3. Funcionalidades - MVP

### 3.1 Autenticação e Perfil
- **Login e Cadastro Seguro**: Integração com **Supabase Auth** para gerenciamento de contas.
- **Perfil do Usuário**: Gerenciamento de dados pessoais e preferências.

### 3.2 Parlamentares (Câmara e Senado)
- **Listagem e Busca**:
  - Visualização unificada de Deputados e Senadores.
  - Filtros por nome, partido e estado (UF).
- **Detalhes do Parlamentar**:
  - **Biografia**: Dados básicos, foto e histórico.
  - **Partidos**: Histórico de filiações.
  - **Despesas**: **Gráficos interativos** detalhando o uso da cota parlamentar.
  - **Discursos**: Histórico recente de pronunciamentos em plenário.
  - **Frentes Parlamentares**: Participação em frentes e grupos de trabalho.
- **Meus Parlamentares**:
  - Funcionalidade de "Favoritar" para acompanhar parlamentares específicos.
  - Acesso rápido aos políticos selecionados.

### 3.3 Proposições e Partidos
- **Listagem de Partidos**: Visualização e busca de legendas partidárias.
- **Proposições (Leis e Projetos)**:
  - Busca por projetos de lei e outras matérias legislativas.
  - **Resumo Inteligente**: Utilização de **Inteligência Artificial (OpenAI)** para gerar resumos explicativos e imparciais sobre o teor e impacto das proposições.

### 3.4 Feed de Notícias Inteligente
- **Atualizações em Tempo Real**: Feed com os acontecimentos mais recentes do Congresso.
- **Resumos com IA**: Cada item do feed conta com um resumo gerado por IA para facilitar o entendimento rápido do contexto político.

## 4. Funcionalidades - Roadmap

### 4.1 Transparência Financeira Expandida
- **Gastos com Emendas**: Monitoramento detalhado de gastos com emenda por deputado.

### 4.2 Atuação em Comissões
- **Detalhamento de Comissões**:
  - Lista de comissões em que o deputado participa.
  - Atuação na comissão: votações, propostas apresentadas e alterações sugeridas.

### 4.3 Feed Comunitário e Temático
- **Feed Personalizado**: Baseado nos deputados seguidos e temas relevantes (Projetos de lei em votação, textos finais de comissões, etc).
- **Filtros de Visualização**:
  - **Mais Novo**: Ordem temporal decrescente.
  - **Em Pauta**: Posts mais votados e com maior interação (Trending).
- **Sistema de Interação**:
  - **Posts**: Sistema de "Likes" e "Dislikes".
  - **Comentários**: Espaço para discussão com sistema de "Upvote" (+1 like) e "Downvote" (-1 like).
- **Busca Integrada**: Aba de pesquisas para encontrar posts específicos por tema dentro do feed.

## 5. Arquitetura Técnica

### Frontend
- **Framework**: React Native com Expo (suporte a iOS e Android).
- **Estilização**: NativeWind (TailwindCSS) para interfaces modernas e responsivas.

### Backend
- **Framework**: Python FastAPI.
- **Função**: Atua como proxy e orquestrador para as APIs de dados abertos, além de gerenciar a lógica de IA.

### Banco de Dados
- **Sistema**: Supabase (PostgreSQL).
- **Dados**: Persistência de usuários, preferências (Meus Parlamentares) e cache de dados.

## 6. Integrações Externas

### APIs de Dados Abertos
- **Câmara dos Deputados**: Fonte primária de dados sobre deputados, despesas e proposições da câmara.
- **Senado Federal**: Fonte de dados sobre senadores e matérias do senado.

### Inteligência Artificial
- **OpenAI API**: Motor de inteligência para:
  - Resumir proposições complexas em linguagem cidadã.
  - Gerar highlights e contextos para o Feed de Notícias.

### Infraestrutura
- **Supabase Auth**: Serviço gerenciado para autenticação segura.
