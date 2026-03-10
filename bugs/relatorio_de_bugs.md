Autor: Helena Oliveira Silva  
Projeto: Desafio QA – Beedoo 2026  
Data da execução dos testes: 09/03/2026



# Relatório de Bugs

Este documento descreve os problemas identificados durante a execução dos testes no módulo de cadastro e listagem de cursos.

---

## BUG 01 – Cadastro de curso permitido com campos vazios

**Severidade:** Alta

**Descrição:**  
O sistema permite cadastrar um curso mesmo quando nenhum campo do formulário é preenchido.

**Passos para reproduzir:**

1. Acessar a aplicação
2. Não preencher nenhum campo do formulário
3. Clicar em "Salvar"

**Resultado atual:**  
O curso é cadastrado e exibido na lista mesmo com todos os campos vazios.

**Resultado esperado:**  
O sistema deveria impedir o cadastro e solicitar o preenchimento dos campos obrigatórios.

---

## BUG 02 – Exclusão de curso não remove item da lista

**Severidade:** Alta

**Descrição:**  
Ao clicar em excluir curso, o sistema apresenta uma mensagem de sucesso, porém o curso continua sendo exibido na lista.

**Passos para reproduzir:**

1. Acessar a aplicação / lista de cursos
2. Clicar na opção "Excluir curso"

**Resultado atual:**  
Mensagem de exclusão exibida, porém o curso permanece na lista.

**Resultado esperado:**  
O curso deveria ser removido da lista após a exclusão.

---

## BUG 03 – Sistema permite cadastro com data de início maior que data de fim

**Severidade:** Média

**Descrição:**  
O sistema permite cadastrar cursos com data de início posterior à data de fim.

**Passos para reproduzir:**

1. Preencher o formulário de cadastro
2. Informar uma data de início posterior à data de fim
3. Clicar em salvar

**Resultado atual:**  
O sistema permite salvar o curso mesmo com datas inconsistentes.

**Resultado esperado:**  
O sistema deveria validar as datas e impedir o cadastro.

---

## BUG 04 – Campo número de vagas aceita valores inválidos

**Severidade:** Média

**Descrição:**  
O campo número de vagas aceita valores inválidos sem apresentar validação adequada.

**Passos para reproduzir:**

1. Acessar o formulário de cadastro
2. Inserir um valor numérico inválido (negativo) no campo número de vagas
3. Salvar o curso

**Resultado atual:**  
O sistema aceita o valor inválido e permite o cadastro.

**Resultado esperado:**  
O sistema deveria validar o campo e aceitar apenas valores numéricos válidos.