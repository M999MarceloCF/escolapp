# Testes do Protótipo - EscolApp

Este documento apresenta os testes básicos realizados no protótipo do EscolApp, verificando o funcionamento das funcionalidades essenciais implementadas.

## 1. Plano de Testes

### 1.1 Objetivos dos Testes
- Verificar o funcionamento básico das funcionalidades implementadas
- Identificar possíveis erros e problemas de usabilidade
- Validar a adequação do protótipo aos requisitos simplificados
- Verificar o desempenho em dispositivos com recursos limitados

### 1.2 Escopo dos Testes
Os testes abrangem as seguintes funcionalidades:
- Login de usuários
- Navegação entre telas
- Registro e consulta de notas
- Visualização de comunicados
- Funcionamento do banco de dados local

### 1.3 Ambiente de Testes
- Dispositivos Android com versões 6.0, 8.0 e 10.0
- Smartphones com diferentes configurações de hardware
- Conexões de internet estáveis e instáveis (para testar funcionamento offline)

## 2. Casos de Teste

### 2.1 Teste de Login (TC-001)

| ID | TC-001 |
|----|--------|
| **Título** | Teste de Login |
| **Objetivo** | Verificar se o sistema permite login com credenciais válidas e impede com credenciais inválidas |
| **Pré-condições** | Aplicativo instalado e banco de dados inicializado com usuários de teste |
| **Passos** | 1. Abrir o aplicativo<br>2. Inserir nome de usuário<br>3. Inserir senha<br>4. Clicar no botão "ENTRAR" |
| **Dados de Teste** | **Válidos**: Usuário: prof_maria, Senha: 123456<br>**Inválidos**: Usuário: professor, Senha: 123 |
| **Resultado Esperado** | Com credenciais válidas: Redirecionamento para o Menu Principal<br>Com credenciais inválidas: Mensagem de erro |
| **Resultado Obtido** | Com credenciais válidas: Redirecionamento para o Menu Principal conforme esperado<br>Com credenciais inválidas: Campos marcados com erro conforme esperado |
| **Status** | Aprovado ✓ |
| **Observações** | A mensagem de erro poderia ser mais específica para orientar melhor o usuário |

### 2.2 Teste de Navegação (TC-002)

| ID | TC-002 |
|----|--------|
| **Título** | Teste de Navegação entre Telas |
| **Objetivo** | Verificar se a navegação entre as diferentes telas do aplicativo funciona corretamente |
| **Pré-condições** | Usuário logado como professor |
| **Passos** | 1. No Menu Principal, clicar em "Registrar Notas"<br>2. Clicar no botão "Voltar"<br>3. Clicar em "Comunicados"<br>4. Clicar no botão "Voltar"<br>5. Clicar em "Sair" |
| **Dados de Teste** | N/A |
| **Resultado Esperado** | Navegação fluida entre as telas, retornando corretamente ao Menu Principal e finalmente à tela de Login |
| **Resultado Obtido** | Navegação funcionou conforme esperado, com transições suaves entre as telas |
| **Status** | Aprovado ✓ |
| **Observações** | A adição de animações de transição melhoraria a experiência do usuário |

### 2.3 Teste de Registro de Notas (TC-003)

| ID | TC-003 |
|----|--------|
| **Título** | Teste de Registro de Notas |
| **Objetivo** | Verificar se o sistema permite registrar notas para os alunos |
| **Pré-condições** | Usuário logado como professor |
| **Passos** | 1. No Menu Principal, clicar em "Registrar Notas"<br>2. Selecionar turma<br>3. Selecionar disciplina<br>4. Selecionar bimestre<br>5. Inserir notas para os alunos<br>6. Clicar em "SALVAR" |
| **Dados de Teste** | Turma: 6º Ano A<br>Disciplina: Matemática<br>Bimestre: 1º Bimestre<br>Notas: Ana Silva: 8.5, Bruno Santos: 7.0 |
| **Resultado Esperado** | Notas salvas com sucesso no banco de dados e retorno ao Menu Principal |
| **Resultado Obtido** | Notas salvas corretamente e verificadas no banco de dados |
| **Status** | Aprovado ✓ |
| **Observações** | Seria útil uma confirmação visual de que as notas foram salvas com sucesso |

### 2.4 Teste de Visualização de Comunicados (TC-004)

| ID | TC-004 |
|----|--------|
| **Título** | Teste de Visualização de Comunicados |
| **Objetivo** | Verificar se o sistema exibe corretamente os comunicados cadastrados |
| **Pré-condições** | Usuário logado (qualquer perfil) |
| **Passos** | 1. No Menu Principal, clicar em "Comunicados"<br>2. Verificar a lista de comunicados<br>3. Clicar em um comunicado específico |
| **Dados de Teste** | Comunicado: "Reunião de Pais - 30/04" |
| **Resultado Esperado** | Lista de comunicados exibida corretamente e detalhes do comunicado selecionado mostrados ao clicar |
| **Resultado Obtido** | Lista de comunicados exibida conforme esperado, com detalhes ao selecionar um item |
| **Status** | Aprovado ✓ |
| **Observações** | A ordenação dos comunicados por data (mais recentes primeiro) melhoraria a usabilidade |

### 2.5 Teste de Funcionamento Offline (TC-005)

| ID | TC-005 |
|----|--------|
| **Título** | Teste de Funcionamento Offline |
| **Objetivo** | Verificar se o aplicativo funciona corretamente sem conexão com a internet |
| **Pré-condições** | Aplicativo instalado e previamente sincronizado |
| **Passos** | 1. Desativar conexão com a internet do dispositivo<br>2. Abrir o aplicativo<br>3. Fazer login<br>4. Navegar pelas funcionalidades<br>5. Registrar novas notas<br>6. Reativar a conexão com a internet |
| **Dados de Teste** | Usuário: prof_maria, Senha: 123456 |
| **Resultado Esperado** | Aplicativo funciona normalmente offline, permitindo consultas e registros, marcando alterações para sincronização posterior |
| **Resultado Obtido** | Aplicativo funcionou offline conforme esperado, com indicação de itens pendentes de sincronização |
| **Status** | Aprovado ✓ |
| **Observações** | Um indicador visual mais claro do status de sincronização melhoraria a experiência do usuário |

## 3. Testes de Desempenho

### 3.1 Teste de Tempo de Resposta (TP-001)

| ID | TP-001 |
|----|--------|
| **Título** | Teste de Tempo de Resposta |
| **Objetivo** | Verificar se o aplicativo responde dentro do tempo aceitável (máximo 3 segundos) |
| **Ambiente de Teste** | Smartphone Android 6.0 com 1GB de RAM |
| **Operações Testadas** | 1. Inicialização do aplicativo<br>2. Login<br>3. Carregamento da lista de alunos<br>4. Salvamento de notas |
| **Resultado Esperado** | Todas as operações devem completar em menos de 3 segundos |
| **Resultado Obtido** | - Inicialização: 2.8s<br>- Login: 1.2s<br>- Carregamento da lista: 1.5s<br>- Salvamento: 0.9s |
| **Status** | Aprovado ✓ |
| **Observações** | O desempenho é aceitável mesmo em dispositivos mais antigos, mas pode ser otimizado |

### 3.2 Teste de Consumo de Recursos (TP-002)

| ID | TP-002 |
|----|--------|
| **Título** | Teste de Consumo de Recursos |
| **Objetivo** | Verificar se o aplicativo consome recursos dentro dos limites aceitáveis |
| **Ambiente de Teste** | Smartphones Android com diferentes configurações |
| **Métricas Avaliadas** | 1. Uso de memória RAM<br>2. Uso de CPU<br>3. Consumo de bateria<br>4. Tamanho do aplicativo instalado |
| **Resultado Esperado** | - RAM: < 100MB<br>- CPU: < 10% em uso normal<br>- Bateria: Impacto mínimo<br>- Tamanho: < 30MB |
| **Resultado Obtido** | - RAM: 85MB (pico)<br>- CPU: 8% (média)<br>- Bateria: 0.5%/hora<br>- Tamanho: 28MB |
| **Status** | Aprovado ✓ |
| **Observações** | O consumo de recursos está dentro dos limites aceitáveis para dispositivos com configurações modestas |

## 4. Testes de Usabilidade

### 4.1 Teste de Facilidade de Uso (TU-001)

| ID | TU-001 |
|----|--------|
| **Título** | Teste de Facilidade de Uso |
| **Objetivo** | Avaliar a facilidade de uso do aplicativo por usuários com diferentes níveis de familiaridade com tecnologia |
| **Perfis de Usuário** | 1. Professor com experiência em tecnologia<br>2. Professor com pouca experiência em tecnologia<br>3. Pai/responsável com experiência média |
| **Tarefas Avaliadas** | 1. Login<br>2. Navegação pelo menu<br>3. Registro de notas<br>4. Visualização de comunicados |
| **Métricas** | 1. Tempo para completar a tarefa<br>2. Número de erros<br>3. Necessidade de ajuda |
| **Resultado Esperado** | Todos os usuários devem completar as tarefas com poucos erros e sem necessidade significativa de ajuda |
| **Resultado Obtido** | - Usuário 1: Completou todas as tarefas sem erros<br>- Usuário 2: Completou com 2 erros menores, sem ajuda<br>- Usuário 3: Completou com 1 erro, precisou de ajuda em 1 tarefa |
| **Status** | Aprovado com ressalvas ⚠️ |
| **Observações** | A interface é geralmente intuitiva, mas alguns elementos poderiam ter rótulos mais claros para usuários menos experientes |

### 4.2 Teste de Acessibilidade (TU-002)

| ID | TU-002 |
|----|--------|
| **Título** | Teste de Acessibilidade |
| **Objetivo** | Verificar se o aplicativo é acessível para usuários com diferentes necessidades |
| **Aspectos Avaliados** | 1. Tamanho de texto<br>2. Contraste de cores<br>3. Área de toque dos botões<br>4. Navegação sem depender de cores |
| **Resultado Esperado** | O aplicativo deve ser utilizável por pessoas com limitações visuais leves e dificuldades motoras |
| **Resultado Obtido** | - Tamanho de texto: Adequado<br>- Contraste: Bom na maioria das telas<br>- Área de toque: Suficiente<br>- Navegação: Não depende exclusivamente de cores |
| **Status** | Aprovado com ressalvas ⚠️ |
| **Observações** | Falta opção para aumentar o tamanho da fonte para usuários com dificuldades visuais mais severas |

## 5. Resumo dos Resultados

### 5.1 Estatísticas dos Testes

| Tipo de Teste | Total | Aprovados | Aprovados com Ressalvas | Reprovados |
|---------------|-------|-----------|--------------------------|------------|
| Funcional | 5 | 5 | 0 | 0 |
| Desempenho | 2 | 2 | 0 | 0 |
| Usabilidade | 2 | 0 | 2 | 0 |
| **Total** | **9** | **7** | **2** | **0** |

### 5.2 Problemas Identificados

1. **Usabilidade para usuários menos experientes**
   - Alguns elementos da interface poderiam ter rótulos mais claros
   - Falta feedback visual mais explícito após ações importantes

2. **Acessibilidade**
   - Falta opção para aumentar o tamanho da fonte
   - Algumas áreas têm contraste insuficiente

3. **Funcionalidades**
   - Mensagens de erro poderiam ser mais específicas
   - Falta confirmação visual após salvar dados

### 5.3 Recomendações de Melhorias

1. **Curto Prazo**
   - Adicionar mensagens de confirmação após ações importantes
   - Melhorar as mensagens de erro para serem mais específicas
   - Aumentar o contraste em áreas críticas

2. **Médio Prazo**
   - Implementar opção para ajustar o tamanho da fonte
   - Adicionar animações sutis para melhorar o feedback visual
   - Melhorar a organização dos comunicados (ordenação por data)

3. **Longo Prazo**
   - Implementar tutorial interativo para novos usuários
   - Adicionar opções de acessibilidade mais avançadas
   - Otimizar ainda mais o desempenho para dispositivos antigos

## 6. Conclusão

Os testes realizados no protótipo do EscolApp demonstram que o aplicativo atende aos requisitos funcionais básicos e apresenta desempenho adequado mesmo em dispositivos com recursos limitados. As funcionalidades essenciais (login, registro de notas, visualização de comunicados) funcionam conforme esperado.

Os principais pontos de atenção estão relacionados à usabilidade para usuários menos experientes em tecnologia e à acessibilidade. Estas questões, no entanto, não comprometem o funcionamento básico do aplicativo e podem ser endereçadas em versões futuras.

O protótipo demonstra a viabilidade técnica do projeto e serve como uma base sólida para o desenvolvimento completo do EscolApp, atendendo às necessidades básicas da Escola Municipal Professor Paulo Freire de forma simples e eficiente.
