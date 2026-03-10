# Desafio QA – Beedoo 2026

## 1. Objetivo do desafio

Este projeto tem como objetivo analisar e testar o módulo de cadastro e listagem de cursos disponibilizado na aplicação fornecida no desafio.

A análise foi realizada considerando aspectos de funcionalidade, validação de dados, comportamento da interface e possíveis inconsistências no fluxo da aplicação.

---

## 2. Ambiente de Teste

Os testes foram executados utilizando o seguinte ambiente:

- Navegador: Google Chrome
- Sistema operacional: Windows
- Tipo de teste: Testes manuais exploratórios
- Aplicação testada: https://creative-sherbet-a51eac.netlify.app/

Os testes foram realizados diretamente na interface da aplicação, simulando o comportamento de um usuário final durante o cadastro e gerenciamento de cursos.

---

## 3. Análise inicial da aplicação

A aplicação apresenta um módulo simples de gestão de cursos, permitindo que usuários realizem o cadastro e visualização de cursos.

O sistema possui um formulário para cadastro contendo campos como:

- Nome do curso
- Descrição
- Instrutor
- URL da imagem de capa
- Data de início
- Data de fim
- Número de vagas
- Tipo de curso (Online ou Presencial)

Dependendo do tipo selecionado, o sistema apresenta um campo adicional:

- Curso online → campo para link de inscrição
- Curso presencial → campo para endereço

Após o cadastro, os cursos são exibidos em uma lista na tela inicial da aplicação (Lista de Cursos).

---

## 4. Fluxos identificados na aplicação

Durante a exploração da aplicação foram identificados os seguintes fluxos principais:

### - Cadastro de curso
O usuário preenche os campos do formulário e salva o curso, que passa a ser exibido na tela inicial da aplicação (Lista de Cursos).

### - Listagem de cursos
Após o cadastro, os cursos são exibidos em uma lista na tela inicial da aplicação (Lista de Cursos).

A listagem não possui:

- paginação
- filtros
- busca
- ordenação customizada

Os cursos são exibidos na ordem em que são criados.

### - Exclusão de curso
Cada curso exibido possui a opção de exclusão.

Ao clicar em excluir, o sistema apresenta uma mensagem de sucesso.

---

## 5. Pontos críticos para teste

Durante a análise da aplicação foram identificados alguns pontos considerados críticos para validação:

- Validação de campos obrigatórios
- Consistência de dados (datas e número de vagas)
- Regras condicionais do formulário (campos exibidos conforme tipo de curso)
- Persistência dos dados cadastrados
- Funcionamento da exclusão de cursos

Esses pontos foram considerados prioritários na criação dos cenários de teste.

---

## 6. Estratégia de criação dos testes

Os cenários de teste foram elaborados considerando:

- Fluxo principal de cadastro de curso
- Exibição de cursos na listagem
- Validação de campos do formulário
- Cenários negativos
- Comportamentos inesperados do sistema

Os testes foram classificados nas seguintes categorias:

- Testes funcionais
- Testes de validação
- Testes de interface
- Testes negativos

Os casos de teste foram documentados em uma planilha no Google Sheets.

---

## 7. Escopo dos Testes

Os testes realizados neste desafio tiveram foco principal nas funcionalidades disponíveis no módulo de cursos da aplicação, incluindo:

- Cadastro de cursos
- Exibição de cursos na lista
- Exclusão de cursos
- Validação de campos do formulário
- Comportamento da interface conforme o tipo de curso selecionado

Não fizeram parte do escopo deste desafio:

- Testes de performance
- Testes de segurança
- Testes de integração com APIs externas
- Testes automatizados

---

## 8. Casos de teste

Os cenários e casos de teste podem ser acessados no link: [Planilha de Casos de Teste](https://docs.google.com/spreadsheets/d/1PrubPGJK3vSG7ktKYG9mdQEDdN-gD68pn5A4yXfhKyQ/edit?usp=sharing)

---

## 9. Matriz de Cobertura de Testes

A matriz de cobertura apresenta a relação entre as principais funcionalidades identificadas na aplicação e os casos de teste criados para validá-las.

| Funcionalidade | Casos de Teste |
|---|---|
| Cadastro de curso | TC01, TC02, TC06 |
| Validação de campos | TC02, TC06, TC08 |
| Regras de interface do formulário | TC03, TC04 |
| Exclusão de curso | TC05 |
| Exibição de cursos na lista | TC07 |
| Cadastro de cursos duplicados | TC09 |

---

## 10. Evidências de execução dos testes

Durante a execução dos testes foram registradas evidências por meio de capturas de tela.

As evidências estão disponíveis no link: [Documento de Evidências de Execução dos Testes](https://docs.google.com/document/d/1bWgcRqblaUE3EH1AD6ifKtbq4aLMSuZtbky4WnmJZ4Q/edit?usp=sharing)

---

## 11. Bugs encontrados

Durante a execução dos testes foram identificados alguns comportamentos inconsistentes no sistema. Os bugs foram identificados a partir da execução dos cenários definidos nos casos de teste e documentados conforme boas práticas de registro de defeitos.

Entre os principais problemas encontrados estão:

- Cadastro de curso permitido com campos vazios
- Exclusão de curso não remove o item da listagem
- Sistema aceita datas inconsistentes (data início maior que data fim)

O relatório detalhado dos bugs pode ser encontrado neste arquivo do repositório: [Relatório de Bugs](/bugs/relatorio_de_bugs.md)


---

## 12. Observações sobre regras de negócio

Durante a análise e execução dos testes foram identificados alguns comportamentos que não necessariamente caracterizam bugs, mas que podem depender da definição de regras de negócio da aplicação.

### - Número de vagas igual a zero

O sistema permite cadastrar cursos com número de vagas igual a zero.

Dependendo da regra de negócio definida para a aplicação, pode ser interessante validar se esse comportamento é esperado, pois normalmente cursos possuem ao menos uma vaga disponível para inscrição.

Caso a intenção seja impedir cursos sem vagas disponíveis, seria recomendável implementar uma validação que limite o valor mínimo do campo.

### - Data de início igual à data de fim

O sistema permite cadastrar cursos com data de início e data de fim iguais.

Esse comportamento pode ser aceitável dependendo da regra de negócio, pois cursos ou eventos de curta duração podem ocorrer em apenas um dia.

Nesse caso, seria importante que a regra de negócio da aplicação definisse claramente se essa situação deve ser permitida.

---

## 13. Uso de Inteligência Artificial

Ferramentas de Inteligência Artificial foram utilizadas como apoio para organização da documentação e estruturação dos cenários de teste.

A análise da aplicação, execução dos testes e validação dos resultados foram realizadas manualmente, garantindo avaliação crítica dos comportamentos observados no sistema.