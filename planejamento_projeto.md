# Planejamento do Projeto - EscolApp

## 1. Cronograma de Desenvolvimento

| Etapa | Descrição | Duração Estimada | Responsável |
|-------|-----------|------------------|-------------|
| 1 | Análise de Requisitos | 2 semanas | Analista de Sistemas |
| 2 | Planejamento | 1 semana | Gerente de Projeto |
| 3 | Prototipação de Interfaces | 2 semanas | Designer de UI/UX |
| 4 | Desenvolvimento do Backend | 3 semanas | Desenvolvedor Python |
| 5 | Desenvolvimento do Frontend | 3 semanas | Desenvolvedor Mobile |
| 6 | Integração e Testes | 2 semanas | Equipe de Testes |
| 7 | Ajustes e Correções | 1 semana | Equipe de Desenvolvimento |
| 8 | Documentação Final | 1 semana | Analista de Sistemas |
| 9 | Implantação | 1 semana | Equipe de Implantação |

**Duração Total Estimada:** 16 semanas (4 meses)

## 2. Matriz de Responsabilidades

| Papel | Responsabilidades | Habilidades Necessárias |
|-------|-------------------|-------------------------|
| Analista de Sistemas | Levantamento e análise de requisitos, documentação | Conhecimento em análise de sistemas, UML, documentação técnica |
| Gerente de Projeto | Planejamento, acompanhamento, gestão de riscos | Gestão de projetos, comunicação, liderança |
| Designer de UI/UX | Prototipação de interfaces, design visual | Design de interfaces mobile, usabilidade, acessibilidade |
| Desenvolvedor Python | Implementação do backend, banco de dados | Python, SQLite, APIs REST |
| Desenvolvedor Mobile | Implementação do frontend com Kivy | Python, Kivy/KivyMD, desenvolvimento mobile |
| Testador | Testes funcionais e de usabilidade | Testes de software, automação de testes |

## 3. Estimativa de Esforço

| Funcionalidade | Complexidade | Esforço (horas) |
|----------------|--------------|-----------------|
| Gestão de Usuários | Média | 40 |
| Gestão de Notas e Frequência | Alta | 60 |
| Comunicação | Média | 40 |
| Calendário Escolar | Baixa | 20 |
| Ocorrências Disciplinares | Média | 30 |
| Relatórios Básicos | Média | 40 |
| Funcionamento Offline | Alta | 50 |
| Gestão de Turmas | Baixa | 20 |
| **Total** | | **300 horas** |

## 4. Recursos Necessários

### 4.1 Recursos Humanos
- 1 Analista de Sistemas
- 1 Gerente de Projeto
- 1 Designer de UI/UX
- 1 Desenvolvedor Python
- 1 Desenvolvedor Mobile
- 1 Testador

### 4.2 Recursos Tecnológicos
- Computadores para desenvolvimento
- Smartphones Android para testes (incluindo modelos mais antigos)
- Servidor para hospedagem do backend
- Ferramentas de desenvolvimento (VS Code, Git, etc.)
- Licenças de software necessárias

## 5. Riscos e Mitigação

| Risco | Probabilidade | Impacto | Estratégia de Mitigação |
|-------|--------------|---------|-------------------------|
| Dificuldade de adaptação dos usuários | Alta | Alto | Treinamento simplificado, tutoriais no app, interface intuitiva |
| Desempenho insatisfatório em dispositivos antigos | Média | Alto | Otimização de código, testes em diversos dispositivos |
| Problemas de sincronização offline | Média | Médio | Testes rigorosos de sincronização, mecanismos de resolução de conflitos |
| Atrasos no desenvolvimento | Média | Médio | Planejamento realista, monitoramento constante, priorização de funcionalidades |
| Resistência à adoção do sistema | Alta | Alto | Envolvimento dos stakeholders desde o início, demonstração de benefícios |

## 6. Plano de Comunicação

| Tipo de Comunicação | Frequência | Participantes | Objetivo |
|---------------------|------------|---------------|----------|
| Reunião de Kickoff | Uma vez | Toda a equipe e cliente | Alinhar expectativas e iniciar o projeto |
| Reuniões de Status | Semanal | Equipe de desenvolvimento | Acompanhar progresso e resolver impedimentos |
| Demonstrações | Quinzenal | Equipe e cliente | Validar funcionalidades desenvolvidas |
| Relatórios de Progresso | Semanal | Gerente e cliente | Informar sobre o andamento do projeto |
| Comunicação de Riscos | Quando necessário | Gerente e stakeholders | Informar sobre riscos identificados |

## 7. Ferramentas e Tecnologias

### 7.1 Desenvolvimento
- **Linguagem**: Python 3.8+
- **Framework UI**: Kivy 2.1.0 / KivyMD 1.1.1
- **Banco de Dados**: SQLite 3
- **Controle de Versão**: Git
- **IDE**: Visual Studio Code
- **Empacotamento**: Buildozer

### 7.2 Gestão de Projeto
- **Gerenciamento de Tarefas**: Trello ou GitHub Projects
- **Documentação**: Markdown, Google Docs
- **Comunicação**: E-mail, WhatsApp, Google Meet

## 8. Critérios de Aceitação

O projeto será considerado concluído e aceito quando:

1. Todas as funcionalidades essenciais estiverem implementadas e funcionando
2. O aplicativo funcionar adequadamente em dispositivos Android 6.0 ou superior
3. O tamanho do aplicativo não exceder 30MB
4. O sistema funcionar corretamente no modo offline
5. Os testes de usabilidade com usuários reais apresentarem resultados satisfatórios
6. A documentação estiver completa e atualizada
7. O cliente aprovar formalmente a entrega

## 9. Estratégia de Implantação

1. **Fase Piloto**: Implantação inicial com um grupo reduzido de usuários (5 professores, 2 funcionários da secretaria, direção e 10 famílias)
2. **Avaliação do Piloto**: Coleta de feedback e ajustes necessários
3. **Treinamento**: Sessões de treinamento simplificadas para cada grupo de usuários
4. **Implantação Completa**: Disponibilização do aplicativo para todos os usuários
5. **Suporte Inicial**: Período de suporte intensivo nas primeiras semanas
6. **Monitoramento e Ajustes**: Acompanhamento contínuo e melhorias incrementais
