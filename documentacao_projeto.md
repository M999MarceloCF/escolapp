# Documentação do Projeto - EscolApp

## 1. Objetivo do Documento

Este documento apresenta a documentação completa do projeto EscolApp, um sistema simplificado de gestão escolar para dispositivos móveis, desenvolvido para a Escola Municipal Professor Paulo Freire. A documentação abrange desde a concepção do projeto até sua implementação, detalhando requisitos, arquitetura, planejamento e protótipos.

## 2. Objetivo do Projeto

O objetivo do projeto EscolApp é desenvolver um aplicativo mobile simples e leve para gestão escolar que atenda às necessidades básicas da Escola Municipal Professor Paulo Freire, proporcionando:

1. Interface intuitiva e de fácil uso, mesmo para usuários com pouca experiência tecnológica
2. Funcionalidades essenciais para a comunicação e gestão escolar básica
3. Baixo consumo de dados e armazenamento
4. Compatibilidade com dispositivos mais antigos e de configuração modesta
5. Possibilidade de uso mesmo com conexão de internet limitada

## 3. Abrangência do Projeto

O EscolApp é um sistema mobile destinado a facilitar a gestão escolar básica, permitindo:
- Registro e consulta de notas e frequência
- Comunicação entre escola e famílias
- Acesso ao calendário escolar
- Registro e acompanhamento de ocorrências disciplinares
- Geração de relatórios básicos

O sistema será utilizado por professores, direção/coordenação, secretaria escolar e pais/responsáveis da Escola Municipal Professor Paulo Freire.

## 4. Definições, Acrônimos e Abreviações

- **EscolApp**: Nome do sistema de gestão escolar mobile
- **RF**: Requisito Funcional
- **RNF**: Requisito Não Funcional
- **RN**: Regra de Negócio
- **UI**: Interface do Usuário (User Interface)
- **UX**: Experiência do Usuário (User Experience)
- **API**: Interface de Programação de Aplicações
- **CRUD**: Create, Read, Update, Delete (Criar, Ler, Atualizar, Excluir)
- **APK**: Android Package (Pacote Android)
- **MVP**: Minimum Viable Product (Produto Mínimo Viável)

## 5. Partes Envolvidas (Stakeholders)

### 5.1 Equipe de Desenvolvimento
- Analista de Sistemas: Responsável pela análise de requisitos e documentação
- Gerente de Projeto: Responsável pelo planejamento e acompanhamento
- Designer de UI/UX: Responsável pelo design da interface
- Desenvolvedor Python: Responsável pela implementação do backend
- Desenvolvedor Mobile: Responsável pela implementação do frontend com Kivy
- Testador: Responsável pelos testes funcionais e de usabilidade

### 5.2 Cliente
- Direção da Escola Municipal Professor Paulo Freire
- Coordenação Pedagógica
- Professores
- Secretaria Escolar
- Pais/Responsáveis
- Alunos

## 6. Resumo dos Envolvidos

### 6.1 Matriz de Papéis e Responsabilidades

| Papel | Responsabilidades |
|-------|-------------------|
| Direção | Aprovação do projeto, definição de requisitos, aprovação de comunicados |
| Coordenação | Acompanhamento pedagógico, definição de requisitos específicos |
| Professores | Registro de notas, frequência e ocorrências |
| Secretaria | Gestão de alunos e turmas, emissão de relatórios |
| Pais/Responsáveis | Acompanhamento do desempenho e frequência dos alunos |
| Alunos | Visualização de notas e comunicados |

## 7. Resumo dos Usuários

### 7.1 Perfis de Usuário

| Perfil | Descrição | Necessidades Principais |
|--------|-----------|-------------------------|
| Direção/Coordenação | Gestores da escola | Visão geral da escola, relatórios, aprovação de comunicados |
| Professores | Docentes da escola | Registro de notas e frequência, comunicação com pais |
| Secretaria | Funcionários administrativos | Gestão de alunos e turmas, relatórios |
| Pais/Responsáveis | Responsáveis pelos alunos | Acompanhamento do desempenho e frequência, recebimento de comunicados |
| Alunos | Estudantes da escola | Visualização de notas e comunicados |

## 8. Descrição da Solução Proposta

O EscolApp é um aplicativo mobile desenvolvido em Python utilizando o framework Kivy/KivyMD, com armazenamento local em SQLite e sincronização quando houver conexão com a internet. O sistema possui uma arquitetura simples baseada no padrão MVC, com foco em baixo consumo de recursos e funcionamento offline.

### 8.1 Principais Funcionalidades

- Gestão de usuários com diferentes perfis de acesso
- Registro e consulta de notas e frequência
- Envio e recebimento de comunicados
- Visualização do calendário escolar
- Registro e acompanhamento de ocorrências disciplinares
- Geração de relatórios básicos
- Funcionamento offline com sincronização posterior

### 8.2 Arquitetura Técnica

- **Frontend**: Kivy/KivyMD (Python)
- **Backend**: Python
- **Banco de Dados Local**: SQLite
- **Sincronização**: API REST simples quando houver conexão

## 9. Cronograma

O projeto será desenvolvido em um período de 16 semanas (4 meses), dividido nas seguintes etapas:

| Etapa | Descrição | Duração |
|-------|-----------|---------|
| 1 | Análise de Requisitos | 2 semanas |
| 2 | Planejamento | 1 semana |
| 3 | Prototipação de Interfaces | 2 semanas |
| 4 | Desenvolvimento do Backend | 3 semanas |
| 5 | Desenvolvimento do Frontend | 3 semanas |
| 6 | Integração e Testes | 2 semanas |
| 7 | Ajustes e Correções | 1 semana |
| 8 | Documentação Final | 1 semana |
| 9 | Implantação | 1 semana |

## 10. Restrições do Projeto

- O aplicativo deve ocupar no máximo 30MB de espaço de armazenamento
- O sistema deve ser compatível com Android 6.0 ou superior
- O sistema deve funcionar adequadamente em dispositivos com configurações modestas
- O sistema deve permitir o funcionamento offline das funcionalidades essenciais
- O desenvolvimento deve utilizar Python como linguagem principal

## 11. Considerações Finais

O EscolApp foi projetado considerando as limitações de recursos da Escola Municipal Professor Paulo Freire e o perfil de seus usuários. O foco na simplicidade, leveza e funcionamento offline visa garantir a usabilidade do sistema mesmo em condições não ideais de infraestrutura tecnológica.

A implementação seguirá uma abordagem incremental, priorizando as funcionalidades essenciais e garantindo que o sistema seja útil mesmo em sua versão inicial. O envolvimento dos usuários finais durante o desenvolvimento será fundamental para garantir a adequação do sistema às necessidades reais da escola.
