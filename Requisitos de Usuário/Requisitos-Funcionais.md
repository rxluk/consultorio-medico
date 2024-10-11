# Requisitos Funcionais - Projeto Consultório Médico

Este documento descreve os requisitos funcionais para o projeto "Consultório Médico", um sistema de gerenciamento para um consultório.

## Requisitos Funcionais

| Identificador | Descrição | Prioridade | Depende de |
| ------------- | ----------- | ---------- | ---------- |
| [RF01] | O sistema deve permitir o cadastro de usuários, incluindo pacientes, médicos e atendentes, com informações detalhadas para cada tipo de usuário. | Alta | - |
| [RF02] | O sistema deve permitir que todos os usuários façam login utilizando credenciais únicas, garantindo a segurança das informações. | Alta | RF01 |
| [RF03] | O atendente deve poder gerenciar o cadastro de pacientes, incluindo adicionar, atualizar e visualizar informações dos pacientes. | Alta | RF01 |
| [RF04] | O atendente deve poder agendar e cancelar consultas para os pacientes, verificando a disponibilidade dos médicos. | Alta | RF01, RF02 |
| [RF05] | O médico deve poder gerenciar sua própria agenda, adicionando, editando ou removendo horários disponíveis para consultas. | Alta | RF02 |
| [RF06] | O médico deve poder registrar detalhes das consultas, como diagnósticos, anotações e prescrições de medicamentos. | Alta | RF04 |
| [RF07] | O sistema deve permitir que os usuários verifiquem o status do pagamento das consultas (Pago, Pendente, Cancelado). | Média | RF01 |
| [RF08] | O técnico de T.I. deve poder gerenciar usuários no sistema, incluindo cadastrar, atualizar e remover médicos e atendentes. | Média | RF01 |
| [RF09] | O sistema deve permitir que os usuários recuperem suas senhas de forma segura através de e-mail. | Média | RF02 |
| [RF10] | O sistema deve fornecer relatórios e estatísticas para administradores e médicos sobre o número de consultas realizadas e receitas geradas. | Baixa | RF06, RF07 |
| [RF11] | O sistema deve permitir a busca de pacientes através de nome, CPF ou data de nascimento para facilitar o gerenciamento. | Média | RF03 |
| [RF12] | O atendente deve poder atribuir um status às consultas agendadas (Agendada, Realizada, Cancelada). | Alta | RF04 |
| [RF13] | O médico deve poder acessar o histórico médico de um paciente antes de realizar uma consulta. | Alta | RF03, RF06 |
| [RF14] | O sistema deve registrar automaticamente a data e hora de todas as consultas realizadas para fins de histórico e relatórios. | Média | RF06 |
| [RF15] | O técnico de T.I. deve poder gerenciar os backups automáticos do banco de dados, garantindo que as informações sejam armazenadas de forma segura. | Média | RF08 |
| [RF16] | O médico deve poder anexar documentos e exames ao histórico médico do paciente durante ou após a consulta. | Média | RF06 |
| [RF17] | O sistema deve alertar o atendente sobre consultas agendadas no mesmo horário para evitar conflitos de agenda. | Alta | RF04 |
| [RF18] | O médico deve poder realizar buscas em seu próprio histórico de consultas para revisar atendimentos passados. | Média | RF06 |
| [RF19] | O administrador deve poder gerenciar permissões de acesso para médicos, atendentes e técnicos. | Alta | RF01, RF08 |
| [RF20] | O atendente deve poder imprimir o resumo da consulta ou receituário, caso solicitado pelo paciente ou médico. | Baixa | RF06 |

## Detalhes dos Requisitos Funcionais

### [RF01] - Cadastro de Usuários

O sistema deve permitir o cadastro de usuários, incluindo pacientes, médicos e atendentes.

- **Dados do Paciente:**
  - Nome completo
  - Data de nascimento
  - CPF
  - Endereço
  - Telefone
  - E-mail
  - Histórico médico

- **Dados do Médico:**
  - Nome completo
  - CRM
  - Especialidade
  - Telefone
  - E-mail
  - Horários de atendimento

- **Dados do Atendente:**
  - Nome completo
  - Cargo
  - Telefone
  - E-mail
  - Data de contratação

### [RF02] - Login e Autenticação

O sistema deve permitir que todos os usuários (pacientes, médicos e atendentes) façam login utilizando credenciais únicas (e-mail e senha).

- **Funcionalidades:**
  - Autenticação segura com criptografia de senhas.
  - Recuperação de senha através de e-mail.
  - Restrição de acesso com base no perfil do usuário.

### [RF03] - Gerenciamento de Pacientes

O atendente deve poder gerenciar o cadastro de pacientes no sistema.

- **Funcionalidades:**
  - **Cadastrar Paciente:** Adicionar novos pacientes com todas as informações necessárias.
  - **Atualizar Dados:** Modificar informações de pacientes existentes.
  - **Visualizar Pacientes:** Acessar e visualizar o histórico médico dos pacientes.

### [RF04] - Agendamento e Cancelamento de Consultas

O atendente deve poder agendar e cancelar consultas para os pacientes, verificando a disponibilidade dos médicos.

- **Funcionalidades:**
  - **Agendar Consulta:** Reservar uma consulta selecionando o médico, data e horário disponíveis.
  - **Cancelar Consulta:** Remover uma consulta previamente agendada.
  - **Validação de Disponibilidade:** Verificar se o horário escolhido está disponível antes de confirmar o agendamento.

### [RF05] - Gerenciamento de Agenda pelo Médico

O médico deve poder gerenciar sua própria agenda, adicionando, editando ou removendo horários disponíveis para consultas.

- **Funcionalidades:**
  - **Adicionar Horários Disponíveis:** Inserir novos horários para consultas.
  - **Editar Horários Disponíveis:** Modificar horários já inseridos.
  - **Remover Horários Disponíveis:** Eliminar horários que não estarão mais disponíveis.
  - **Visualização em Formato de Calendário:** Verificar consultas agendadas em um formato de calendário.

### [RF06] - Registro de Consultas pelo Médico

O médico deve poder registrar detalhes das consultas, como diagnósticos, anotações e prescrições de medicamentos.

- **Funcionalidades:**
  - **Registrar Diagnóstico:** Adicionar informações sobre o diagnóstico do paciente.
  - **Registrar Anotações:** Anotar observações sobre o atendimento.
  - **Prescrições de Medicamentos:** Indicar dosagens e instruções de uso.
  - **Associar Consulta ao Status:** Indicar se a consulta foi realizada ou cancelada.

### [RF07] - Verificação de Pagamento

O sistema deve permitir que os usuários verifiquem o status do pagamento das consultas.

- **Funcionalidades:**
  - **Exibir Status do Pagamento:** Indicar se a consulta já foi paga, está pendente ou foi cancelada.
  - **Atualizar Status de Pagamento:** Alterar o status conforme necessário.

### [RF08] - Gerenciamento de Usuários pelo Técnico de T.I.

O técnico de T.I. deve poder gerenciar usuários no sistema, incluindo cadastrar, atualizar e remover médicos e atendentes.

- **Funcionalidades:**
  - **Cadastrar Usuários:** Adicionar novos médicos e atendentes.
  - **Atualizar Dados de Usuários:** Modificar informações de médicos e atendentes existentes.
  - **Remover Usuários:** Eliminar médicos e atendentes do sistema.
  - **Gerenciar Permissões:** Atribuir e modificar permissões de acesso conforme necessário.

### [RF09] - Recuperação de Senha

O sistema deve permitir que os usuários recuperem suas senhas de forma segura através de e-mail.

- **Funcionalidades:**
  - **Solicitar Recuperação:** Enviar um e-mail com link para redefinição de senha.
  - **Redefinir Senha:** Permitir que o usuário defina uma nova senha através do link recebido.

### [RF10] - Relatórios e Estatísticas

O sistema deve fornecer relatórios e estatísticas para administradores e médicos sobre o número de consultas realizadas e receitas geradas.

- **Funcionalidades:**
  - **Gerar Relatórios de Consultas:** Mostrar o número de consultas realizadas em um determinado período.
  - **Gerar Relatórios de Receitas:** Exibir a receita gerada por consultas e pagamentos.
  - **Histórico de Atendimentos:** Visualizar o histórico de atendimentos por médico e paciente.

### [RF11] - Busca de Pacientes

O sistema deve permitir a busca de pacientes utilizando diferentes critérios para facilitar o gerenciamento de seus dados.

- **Entradas:**
  - Nome do paciente.
  - CPF do paciente.
  - Data de nascimento.

- **Processamento:**
  - O sistema realiza uma busca no banco de dados com base nos critérios fornecidos.

- **Saídas:**
  - Lista de pacientes que correspondem à busca, permitindo o acesso aos seus detalhes.

### [RF12] - Atribuição de Status às Consultas

O atendente deve poder alterar o status de uma consulta conforme necessário.

- **Funcionalidades:**
  - **Agendada:** A consulta está programada para ocorrer.
  - **Realizada:** A consulta foi concluída.
  - **Cancelada:** A consulta foi desmarcada.

### [RF13] - Acesso ao Histórico Médico do Paciente

O médico deve poder visualizar o histórico médico do paciente antes de realizar uma consulta.

- **Funcionalidades:**
  - **Visualização:** Exibir consultas anteriores, diagnósticos e prescrições.
  - **Anexos:** Exibir documentos ou exames anexados ao histórico.

### [RF14] - Registro Automático de Consultas

O sistema deve registrar automaticamente a data e hora de todas as consultas realizadas.

- **Funcionalidades:**
  - Gravação automática de data e hora ao final de cada consulta.
  - Histórico acessível para fins de relatórios ou revisões.

### [RF15] - Gerenciamento de Backups

O técnico de T.I. deve poder configurar e gerenciar backups automáticos do banco de dados.

- **Funcionalidades:**
  - Definir frequência de backups.
  - Monitorar o sucesso ou falha dos backups.
  - Restaurar dados de backups anteriores, se necessário.

### [RF16] - Anexar Documentos e Exames

O médico deve poder anexar documentos e exames ao histórico médico do paciente durante ou após a consulta.

- **Funcionalidades:**
  - Upload de arquivos como PDFs, imagens de exames ou relatórios médicos.
  - Visualização de anexos ao acessar o histórico do paciente.

### [RF17] - Alerta de Conflito de Consultas

O sistema deve alertar o atendente sobre possíveis conflitos de agenda ao tentar agendar consultas no mesmo horário.

- **Funcionalidades:**
  - Exibir aviso de conflito ao selecionar horários já reservados.
  - Opção de sugerir horários alternativos disponíveis.

### [RF18] - Busca no Histórico de Consultas

O médico deve poder realizar buscas em seu próprio histórico de consultas para revisar atendimentos passados.

- **Funcionalidades:**
  - Busca por nome de paciente ou data.
  - Acesso a diagnósticos e prescrições registrados anteriormente.

### [RF19] - Gerenciamento de Permissões

O administrador deve poder gerenciar permissões de acesso para os diferentes perfis de usuários (médicos, atendentes e técnicos).

- **Funcionalidades:**
  - Definir quem pode acessar e editar quais informações.
  - Atribuir ou revogar permissões com base na função do usuário.

### [RF20] - Impressão de Resumo da Consulta

O atendente deve poder imprimir um resumo da consulta ou receituário quando solicitado.

- **Funcionalidades:**
  - Exibir botão de impressão para gerar resumo da consulta.
  - Enviar para uma impressora configurada.

---

## Resumo das Funcionalidades por Perspectiva

| **Perspectiva**    | **Requisitos Funcionais**                                                                            |
|--------------------|------------------------------------------------------------------------------------------------------|
| **Sistema**        | RF01 - Cadastro de Usuários, RF02 - Login e Autenticação, RF03 - Controle de Acesso                 |
| **Atendente**      | RF03 - Gerenciamento de Pacientes, RF04 - Agendamento e Cancelamento de Consultas                   |
| **Médico**         | RF05 - Gerenciamento de Agenda, RF06 - Registro de Consultas, RF10 - Relatórios e Estatísticas         |
| **T.I./Técnico**   | RF08 - Gerenciamento de Usuários, RF09 - Recuperação de Senha                                        |
| **Adicionais**     | RF07 - Verificação de Pagamento                                                                        |

---

## Considerações Finais

- **Clareza e Organização:** Os requisitos estão organizados de acordo com as diferentes perspectivas de uso, facilitando a compreensão e a implementação.
- **Separação de Responsabilidades:** Cada tipo de usuário tem funcionalidades específicas, garantindo uma experiência personalizada e eficiente.
- **Segurança e Controle de Acesso:** A implementação de login e controle de acesso garante que apenas usuários autorizados possam acessar e modificar informações sensíveis.
- **Simplificação nos Pagamentos:** A funcionalidade de verificação de pagamento foca apenas no status do pagamento, evitando complicações no processamento direto.

---
