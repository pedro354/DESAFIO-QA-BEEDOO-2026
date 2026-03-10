# DESAFIO-QA-BEEDOO-2026

## Análise inicial da aplicação

### Objetivo da aplicação

A aplicação tem como objetivo permitir o **cadastro e gerenciamento de cursos**, possibilitando ao usuário:

* cadastrar novos cursos
* visualizar cursos cadastrados em formato de cards
* excluir cursos existentes

Trata-se de um sistema simples de gerenciamento de cursos, provavelmente utilizado para fins educacionais ou administrativos.

---

## Principais fluxos disponíveis

Durante a exploração da aplicação foram identificados os seguintes fluxos principais:

### Cadastro de curso

O usuário pode cadastrar um curso preenchendo os seguintes campos:

* Nome do curso
* Descrição do curso
* Instrutor
* URL da imagem de capa
* Data de início
* Data de fim
* Número de vagas
* Tipo de curso (Presencial ou Online)

Após o preenchimento, o botão **Cadastrar Curso** permite registrar o curso no sistema.

---

### Listagem de cursos

Os cursos cadastrados são exibidos em formato de **cards**, contendo:

* imagem de capa
* tipo do curso
* nome
* descrição
* data de início
* data de fim
* número de vagas

Cada card também possui um botão de **exclusão do curso**.

---

## Pontos críticos para teste

Durante a análise foram identificados alguns pontos críticos que devem ser priorizados em testes:

* validação de campos obrigatórios
* comportamento do botão de cadastro
* renderização correta da listagem de cursos
* funcionamento da exclusão de cursos
* consistência das datas (início e fim)
* validação do número de vagas

---

# Bugs encontrados

## Bug 1 — Cadastro de curso com campos vazios

### Passos para reproduzir

1. Acessar a página **Cadastrar Curso**
2. Deixar todos os campos vazios
3. Clicar no botão **Cadastrar Curso**
4. Acessar a página **Listar Cursos**

### Resultado atual

O sistema permite o cadastro de cursos **sem preenchimento dos campos obrigatórios**, resultando em cursos vazios na listagem.

### Resultado esperado

O sistema deveria validar os campos obrigatórios antes do cadastro, impedindo o envio do formulário.

Possível comportamento esperado:

* destaque visual nos campos obrigatórios (ex: borda vermelha)
* mensagem de erro informando que o preenchimento é obrigatório

### Severidade

Alta

Cursos inválidos podem ser cadastrados no sistema, gerando inconsistência de dados e comprometendo a qualidade das informações.

---

## Bug 2 — Exclusão de curso não atualiza a listagem

### Passos para reproduzir

1. Cadastrar um novo curso
2. Acessar a página **Listar Cursos**
3. Clicar no botão **Excluir Curso**

### Resultado atual

Uma notificação de exclusão é exibida, porém o curso **continua visível na listagem de cursos**.

### Resultado esperado

O curso deveria ser removido da listagem imediatamente após a exclusão.

### Severidade

Média

Esse comportamento pode gerar confusão ao usuário, pois aparenta que o curso não foi removido do sistema.

---

## Uso de Inteligência Artificial

Durante o desafio utilizei ferramentas de IA como apoio para:

* revisão da documentação
* melhoria da organização textual
* validação da clareza dos cenários descritos

A análise da aplicação, identificação dos fluxos e detecção dos bugs foram realizadas manualmente durante a exploração da aplicação.

---
## Evidências:
Link: https://drive.google.com/drive/folders/1rA8apozBXVap8ts7ZNeZqWaghF_k70WO?usp=drive_link
