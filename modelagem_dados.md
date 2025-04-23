# Modelagem de Dados - EscolApp

## Diagrama de Entidade-Relacionamento Simplificado

```
+-------------+       +-------------+       +-------------+
|   Usuario   |       |    Turma    |       | Disciplina  |
+-------------+       +-------------+       +-------------+
| id          |       | id          |       | id          |
| nome        |       | nome        |       | nome        |
| login       |       | ano         |       | descricao   |
| senha       |       | periodo     |       +-------------+
| tipo        |       +-------------+              |
| email       |             |                      |
| telefone    |             |                      |
+-------------+             |                      |
      |                     |                      |
      |                     |                      |
+-------------+       +-------------+       +-------------+
|    Aluno    |       | Professor   |       | Prof_Disc   |
+-------------+       +-------------+       +-------------+
| id          |       | id          |       | professor_id|
| usuario_id  |       | usuario_id  |       | disciplina_id|
| turma_id    |       +-------------+       | turma_id    |
| matricula   |             |              +-------------+
+-------------+             |
      |                     |
      |                     |
+-------------+       +-------------+       +-------------+
|    Nota     |       | Frequencia  |       | Comunicado  |
+-------------+       +-------------+       +-------------+
| id          |       | id          |       | id          |
| aluno_id    |       | aluno_id    |       | titulo      |
| disciplina_id|       | disciplina_id|      | conteudo    |
| bimestre    |       | data        |       | data        |
| valor       |       | presente    |       | autor_id    |
+-------------+       +-------------+       | aprovado    |
                                           | turma_id    |
                                           +-------------+
                                                  |
+-------------+       +-------------+             |
| Ocorrencia  |       | Calendario  |             |
+-------------+       +-------------+             |
| id          |       | id          |             |
| aluno_id    |       | titulo      |             |
| data        |       | descricao   |             |
| descricao   |       | data        |             |
| gravidade   |       | tipo        |             |
| autor_id    |       +-------------+             |
+-------------+                                   |
                                                  |
                                           +-------------+
                                           | Notificacao |
                                           +-------------+
                                           | id          |
                                           | usuario_id  |
                                           | titulo      |
                                           | mensagem    |
                                           | data        |
                                           | lida        |
                                           | tipo        |
                                           +-------------+
```

## Descrição das Entidades

### Usuario
- Armazena informações básicas de todos os usuários do sistema
- Atributos:
  - id: Identificador único
  - nome: Nome completo do usuário
  - login: Nome de usuário para acesso
  - senha: Senha de acesso (armazenada com hash)
  - tipo: Tipo de usuário (diretor, coordenador, professor, secretaria, pai/responsável, aluno)
  - email: Endereço de e-mail
  - telefone: Número de telefone

### Aluno
- Armazena informações específicas dos alunos
- Atributos:
  - id: Identificador único
  - usuario_id: Referência ao usuário correspondente
  - turma_id: Referência à turma do aluno
  - matricula: Número de matrícula do aluno

### Professor
- Armazena informações específicas dos professores
- Atributos:
  - id: Identificador único
  - usuario_id: Referência ao usuário correspondente

### Turma
- Representa as turmas da escola
- Atributos:
  - id: Identificador único
  - nome: Nome da turma (ex: "6º Ano A")
  - ano: Ano letivo
  - periodo: Período (manhã, tarde)

### Disciplina
- Representa as disciplinas oferecidas
- Atributos:
  - id: Identificador único
  - nome: Nome da disciplina
  - descricao: Descrição breve da disciplina

### Prof_Disc
- Tabela de relacionamento entre professores, disciplinas e turmas
- Atributos:
  - professor_id: Referência ao professor
  - disciplina_id: Referência à disciplina
  - turma_id: Referência à turma

### Nota
- Armazena as notas dos alunos
- Atributos:
  - id: Identificador único
  - aluno_id: Referência ao aluno
  - disciplina_id: Referência à disciplina
  - bimestre: Bimestre (1, 2, 3 ou 4)
  - valor: Valor da nota (0 a 10)

### Frequencia
- Registra a frequência dos alunos
- Atributos:
  - id: Identificador único
  - aluno_id: Referência ao aluno
  - disciplina_id: Referência à disciplina
  - data: Data da aula
  - presente: Indicador de presença (verdadeiro/falso)

### Comunicado
- Armazena comunicados enviados pela escola
- Atributos:
  - id: Identificador único
  - titulo: Título do comunicado
  - conteudo: Conteúdo do comunicado
  - data: Data de criação
  - autor_id: Referência ao usuário que criou o comunicado
  - aprovado: Indicador de aprovação pela direção
  - turma_id: Referência à turma destinatária (null para toda a escola)

### Ocorrencia
- Registra ocorrências disciplinares
- Atributos:
  - id: Identificador único
  - aluno_id: Referência ao aluno
  - data: Data da ocorrência
  - descricao: Descrição da ocorrência
  - gravidade: Nível de gravidade (baixa, média, alta)
  - autor_id: Referência ao usuário que registrou a ocorrência

### Calendario
- Armazena eventos do calendário escolar
- Atributos:
  - id: Identificador único
  - titulo: Título do evento
  - descricao: Descrição do evento
  - data: Data do evento
  - tipo: Tipo de evento (feriado, reunião, prova, etc.)

### Notificacao
- Armazena notificações enviadas aos usuários
- Atributos:
  - id: Identificador único
  - usuario_id: Referência ao usuário destinatário
  - titulo: Título da notificação
  - mensagem: Conteúdo da notificação
  - data: Data de envio
  - lida: Indicador de leitura
  - tipo: Tipo de notificação (nota, frequência, comunicado, etc.)

## Relacionamentos Principais

1. Um **Usuário** pode ser um **Aluno** ou um **Professor** (relacionamento 1:1)
2. Um **Aluno** pertence a uma **Turma** (relacionamento N:1)
3. Um **Professor** pode lecionar várias **Disciplinas** em várias **Turmas** (relacionamento N:M através de Prof_Disc)
4. Um **Aluno** pode ter várias **Notas** em diferentes **Disciplinas** (relacionamento 1:N)
5. Um **Aluno** pode ter vários registros de **Frequência** (relacionamento 1:N)
6. Um **Comunicado** pode ser direcionado a uma **Turma** específica ou a toda a escola
7. Uma **Ocorrência** está associada a um **Aluno** específico
8. Uma **Notificação** é enviada para um **Usuário** específico

## Observações sobre a Implementação

1. Este modelo será implementado usando SQLite para armazenamento local no dispositivo
2. Para simplificar a sincronização offline, cada registro terá campos adicionais:
   - `sync_status`: Status de sincronização (sincronizado, pendente, conflito)
   - `last_updated`: Data da última atualização
   - `device_id`: Identificador do dispositivo que fez a última atualização
3. Índices serão criados para campos frequentemente consultados para otimizar o desempenho
4. O modelo é intencionalmente simplificado para atender às necessidades básicas da escola pública, mantendo o banco de dados leve e eficiente
