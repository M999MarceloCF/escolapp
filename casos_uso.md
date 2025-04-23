# Diagrama de Casos de Uso - EscolApp

```
+-------------------------------------------------------------+
|                        EscolApp                             |
+-------------------------------------------------------------+
                            |
  +------------------------+------------------------+
  |                        |                        |
+---------------------+ +---------------------+ +---------------------+
|     Professor       | |   Pais/Responsáveis | |  Direção/Coordenação|
+---------------------+ +---------------------+ +---------------------+
| - Registrar notas   | | - Visualizar notas  | | - Gerenciar usuários|
| - Registrar         | | - Visualizar        | | - Aprovar           |
|   frequência        | |   frequência        | |   comunicados       |
| - Registrar         | | - Visualizar        | | - Gerenciar         |
|   ocorrências       | |   ocorrências       | |   calendário        |
| - Visualizar turmas | | - Receber           | | - Visualizar        |
|                     | |   comunicados       | |   relatórios        |
+---------------------+ +---------------------+ +---------------------+
                            |
                  +---------------------+
                  |      Secretaria     |
                  +---------------------+
                  | - Gerenciar alunos  |
                  | - Gerenciar turmas  |
                  | - Gerar relatórios  |
                  | - Enviar comunicados|
                  +---------------------+
```

## Descrição dos Casos de Uso

### Atores

1. **Professor**
   - Profissional responsável por ministrar aulas e avaliar os alunos

2. **Pais/Responsáveis**
   - Responsáveis pelos alunos que acompanham seu desempenho escolar

3. **Direção/Coordenação**
   - Gestores da escola responsáveis pela administração geral

4. **Secretaria**
   - Funcionários responsáveis pelo gerenciamento administrativo da escola

### Casos de Uso

#### Professor

1. **Registrar notas**
   - **Descrição**: O professor registra as notas das avaliações dos alunos
   - **Fluxo principal**:
     1. Professor acessa o sistema
     2. Seleciona a turma e disciplina
     3. Seleciona o bimestre
     4. Insere as notas dos alunos
     5. Salva as informações

2. **Registrar frequência**
   - **Descrição**: O professor registra a presença ou ausência dos alunos
   - **Fluxo principal**:
     1. Professor acessa o sistema
     2. Seleciona a turma e disciplina
     3. Seleciona a data
     4. Marca presença/ausência para cada aluno
     5. Salva as informações

3. **Registrar ocorrências**
   - **Descrição**: O professor registra ocorrências disciplinares dos alunos
   - **Fluxo principal**:
     1. Professor acessa o sistema
     2. Seleciona a turma e o aluno
     3. Descreve a ocorrência
     4. Classifica a gravidade
     5. Salva a ocorrência

4. **Visualizar turmas**
   - **Descrição**: O professor visualiza as turmas e alunos sob sua responsabilidade
   - **Fluxo principal**:
     1. Professor acessa o sistema
     2. Visualiza lista de turmas
     3. Seleciona uma turma para ver detalhes
     4. Visualiza lista de alunos da turma

#### Pais/Responsáveis

1. **Visualizar notas**
   - **Descrição**: Os pais visualizam as notas de seus filhos
   - **Fluxo principal**:
     1. Pais acessam o sistema
     2. Visualizam as notas por disciplina e bimestre

2. **Visualizar frequência**
   - **Descrição**: Os pais visualizam a frequência de seus filhos
   - **Fluxo principal**:
     1. Pais acessam o sistema
     2. Visualizam o registro de frequência

3. **Visualizar ocorrências**
   - **Descrição**: Os pais visualizam ocorrências disciplinares de seus filhos
   - **Fluxo principal**:
     1. Pais acessam o sistema
     2. Visualizam lista de ocorrências

4. **Receber comunicados**
   - **Descrição**: Os pais recebem comunicados da escola
   - **Fluxo principal**:
     1. Pais acessam o sistema
     2. Visualizam comunicados recebidos

#### Direção/Coordenação

1. **Gerenciar usuários**
   - **Descrição**: A direção gerencia os usuários do sistema
   - **Fluxo principal**:
     1. Direção acessa o sistema
     2. Cadastra, edita ou remove usuários
     3. Define perfis de acesso

2. **Aprovar comunicados**
   - **Descrição**: A direção aprova comunicados antes do envio
   - **Fluxo principal**:
     1. Direção acessa o sistema
     2. Visualiza comunicados pendentes
     3. Aprova ou rejeita comunicados

3. **Gerenciar calendário**
   - **Descrição**: A direção gerencia o calendário escolar
   - **Fluxo principal**:
     1. Direção acessa o sistema
     2. Cadastra, edita ou remove eventos
     3. Publica o calendário

4. **Visualizar relatórios**
   - **Descrição**: A direção visualiza relatórios gerenciais
   - **Fluxo principal**:
     1. Direção acessa o sistema
     2. Seleciona o tipo de relatório
     3. Visualiza ou exporta o relatório

#### Secretaria

1. **Gerenciar alunos**
   - **Descrição**: A secretaria gerencia o cadastro de alunos
   - **Fluxo principal**:
     1. Secretaria acessa o sistema
     2. Cadastra, edita ou remove alunos
     3. Associa alunos a turmas

2. **Gerenciar turmas**
   - **Descrição**: A secretaria gerencia as turmas
   - **Fluxo principal**:
     1. Secretaria acessa o sistema
     2. Cadastra, edita ou remove turmas
     3. Associa professores às turmas

3. **Gerar relatórios**
   - **Descrição**: A secretaria gera relatórios administrativos
   - **Fluxo principal**:
     1. Secretaria acessa o sistema
     2. Seleciona o tipo de relatório
     3. Define parâmetros
     4. Gera e imprime o relatório

4. **Enviar comunicados**
   - **Descrição**: A secretaria envia comunicados após aprovação
   - **Fluxo principal**:
     1. Secretaria acessa o sistema
     2. Cria comunicado
     3. Submete para aprovação
     4. Envia após aprovação
