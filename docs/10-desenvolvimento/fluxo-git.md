# Fluxo de Git

## 1. Objetivo

Este documento define o fluxo de versionamento e colaboração
utilizado no projeto Sistema de Gestão para Barbearias.

O objetivo é manter um histórico organizado, facilitar Code Review,
reduzir alterações não revisadas e estabelecer um processo consistente
para evolução do projeto.

---

## 2. Branches

O projeto utiliza as seguintes categorias de branches:

### master

Branch principal do projeto.

Representa versões oficialmente liberadas.

Alterações não devem ser realizadas diretamente nesta branch.

---

### develop

Branch de integração do desenvolvimento.

Recebe alterações provenientes das branches de feature após o
processo de Pull Request e Code Review.

---

### feature/*

Branches utilizadas para desenvolvimento de funcionalidades ou
alterações específicas.

Exemplos:

- `feature/agendamento`
- `feature/cadastro-cliente`
- `feature/controle-financeiro`

As branches de feature são criadas a partir de `develop`.

---

### release/*

Branches utilizadas para preparação de uma versão que será
liberada.

Exemplo:

- `release/1.0.0`

Não serão criadas release branches enquanto não existir uma versão
efetivamente pronta para liberação.

---

### hotfix/*

Branches utilizadas para correções urgentes em versões de produção.

Exemplo:

- `hotfix/corrige-calculo-faturamento`

Após a correção, as alterações devem ser incorporadas tanto à
`master` quanto à `develop`.

---

## 3. Fluxo

O fluxo principal é:

```text
feature/*
    ↓
Pull Request + Code Review
    ↓
develop
    ↓
release/*
    ↓
master

Em caso de correções urgentes:

master
   ↓
hotfix/*
   ↓
master
   ↓
develop