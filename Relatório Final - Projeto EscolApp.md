# Relatório Final - Projeto EscolApp

## 1. Introdução

Este relatório apresenta o desenvolvimento do EscolApp, um sistema simplificado de gestão escolar para dispositivos móveis, projetado especificamente para atender às necessidades da Escola Municipal Professor Paulo Freire. O projeto foi desenvolvido como parte do Projeto Multidisciplinar Final do curso de Análise e Desenvolvimento de Sistemas, seguindo as diretrizes e etapas estabelecidas.

O EscolApp foi concebido como uma solução simples e leve, adequada à realidade de uma escola pública com recursos limitados, permitindo o registro e consulta de notas e frequência, comunicação entre escola e famílias, acesso ao calendário escolar e registro de ocorrências disciplinares, mesmo em dispositivos móveis mais antigos e com conexão de internet limitada.

## 2. Objetivos do Projeto

O objetivo principal do projeto foi desenvolver um aplicativo mobile simples e leve para gestão escolar que atendesse às necessidades básicas da Escola Municipal Professor Paulo Freire, proporcionando:

1. Interface intuitiva e de fácil uso, mesmo para usuários com pouca experiência tecnológica
2. Funcionalidades essenciais para a comunicação e gestão escolar básica
3. Baixo consumo de dados e armazenamento
4. Compatibilidade com dispositivos mais antigos e de configuração modesta
5. Possibilidade de uso mesmo com conexão de internet limitada

## 3. Metodologia

O desenvolvimento do projeto seguiu as etapas estabelecidas no manual do Projeto Multidisciplinar Final:

### Etapa 1

**META 1 - Pesquisa e Análise**: Foram pesquisados e analisados diferentes modelos de projetos de software para gestão escolar, identificando funcionalidades comuns e boas práticas para aplicações mobile.

**META 2 - Escolha do Tema e Cliente**: Foi definido como tema o desenvolvimento de um sistema de gestão escolar mobile para a Escola Municipal Professor Paulo Freire, uma instituição pública de ensino fundamental.

**META 3 - Comunicação e Levantamento de Requisitos**: Foi realizada uma entrevista fictícia com o diretor da escola para entender as necessidades e desafios enfrentados, resultando no levantamento de requisitos funcionais e não funcionais.

**META 4 - Análise de Requisitos**: Os requisitos foram analisados e a viabilidade técnica do projeto foi avaliada, definindo as tecnologias a serem utilizadas (Python com Kivy/KivyMD).

**META 5 - Planejamento**: Foi elaborado um cronograma de desenvolvimento, estimativas de esforço, matriz de responsabilidades e análise de riscos.

**META 6 - Preparação da Documentação**: Toda a documentação do projeto foi organizada, incluindo objetivos, escopo, requisitos, diagramas e protótipos de interface.

### Etapa 2

**META 1 - Implementação**: Foi desenvolvido um protótipo funcional do aplicativo, implementando as funcionalidades essenciais como login, registro de notas e visualização de comunicados.

**META 2 - Testes e Homologação**: Foram realizados testes funcionais, de desempenho e de usabilidade para validar o protótipo e identificar oportunidades de melhoria.

**META 3 - Relatório Final e Vídeo**: Este relatório final foi elaborado, documentando todo o processo de desenvolvimento, e um vídeo de apresentação foi preparado para demonstrar o funcionamento do sistema.

## 4. Desenvolvimento

### 4.1 Análise de Requisitos

Com base na entrevista com o cliente fictício, foram identificados os seguintes requisitos:

**Requisitos Funcionais**:
- Gestão de usuários com diferentes perfis
- Registro e consulta de notas e frequência
- Envio e recebimento de comunicados
- Visualização do calendário escolar
- Registro de ocorrências disciplinares
- Geração de relatórios básicos
- Funcionamento offline com sincronização posterior

**Requisitos Não Funcionais**:
- Interface simples e intuitiva
- Desempenho adequado em dispositivos com configurações modestas
- Compatibilidade com Android 6.0 ou superior
- Disponibilidade offline das funcionalidades básicas
- Segurança básica de dados
- Tamanho máximo do aplicativo de 30MB

### 4.2 Modelagem de Dados

Foi desenvolvido um modelo de dados simplificado, utilizando SQLite para armazenamento local, com as seguintes entidades principais:
- Usuários (professores, direção, secretaria, pais/responsáveis, alunos)
- Turmas
- Disciplinas
- Notas
- Frequência
- Comunicados
- Ocorrências

O modelo foi projetado para facilitar o funcionamento offline, incluindo campos para controle de sincronização.

### 4.3 Arquitetura do Sistema

O EscolApp foi desenvolvido utilizando:
- **Frontend**: Kivy/KivyMD (Python)
- **Backend**: Python
- **Banco de Dados Local**: SQLite
- **Padrão Arquitetural**: MVC (Model-View-Controller)

A arquitetura foi projetada para ser simples e eficiente, permitindo o funcionamento offline e a sincronização quando houver conexão com a internet.

### 4.4 Implementação do Protótipo

O protótipo implementado inclui:
- Sistema de login com diferentes perfis de usuário
- Menu principal adaptado ao perfil do usuário
- Tela de registro e consulta de notas
- Visualização de comunicados
- Banco de dados local com dados de exemplo

A implementação focou nas funcionalidades essenciais, mantendo o código simples e otimizado para dispositivos com recursos limitados.

### 4.5 Testes Realizados

Foram realizados diversos testes para validar o protótipo:
- **Testes Funcionais**: Login, navegação, registro de notas, visualização de comunicados, funcionamento offline
- **Testes de Desempenho**: Tempo de resposta e consumo de recursos
- **Testes de Usabilidade**: Facilidade de uso e acessibilidade

Os resultados dos testes foram positivos, demonstrando que o protótipo atende aos requisitos básicos e tem desempenho adequado mesmo em dispositivos com recursos limitados.

## 5. Resultados Obtidos

O principal resultado do projeto foi o desenvolvimento de um protótipo funcional do EscolApp, que demonstra a viabilidade técnica da solução proposta. O protótipo implementa as funcionalidades essenciais e atende aos requisitos não funcionais estabelecidos, especialmente em relação à simplicidade, leveza e funcionamento offline.

Os testes realizados confirmaram que o aplicativo:
- Funciona adequadamente em dispositivos com recursos limitados
- Consome poucos recursos (memória, CPU, armazenamento)
- Permite o registro e consulta de informações mesmo sem conexão com a internet
- Possui interface simples e intuitiva, adequada para usuários com diferentes níveis de familiaridade com tecnologia

Foram identificadas algumas oportunidades de melhoria, principalmente relacionadas à usabilidade para usuários menos experientes e à acessibilidade, que poderiam ser implementadas em versões futuras.

## 6. Conclusões

O desenvolvimento do EscolApp demonstrou que é possível criar soluções tecnológicas simples e eficientes para atender às necessidades básicas de instituições públicas com recursos limitados. O projeto atingiu seus objetivos principais, resultando em um protótipo funcional que poderia ser expandido e implementado em um ambiente real.

As principais lições aprendidas durante o desenvolvimento foram:
1. A importância de entender profundamente as necessidades e limitações do cliente
2. O valor de manter a simplicidade e o foco nas funcionalidades essenciais
3. A necessidade de considerar o contexto de uso e as limitações tecnológicas dos usuários
4. A viabilidade de utilizar Python com Kivy para desenvolvimento de aplicações mobile leves

### 6.1 Contribuições do Projeto

O EscolApp contribui para a área de desenvolvimento de sistemas ao demonstrar como tecnologias modernas podem ser adaptadas para contextos com recursos limitados, sem comprometer a funcionalidade essencial. O projeto também evidencia a importância de considerar o contexto social e econômico no desenvolvimento de soluções tecnológicas.

### 6.2 Trabalhos Futuros

Com base nos resultados obtidos e nas oportunidades de melhoria identificadas, sugerimos os seguintes trabalhos futuros:
1. Implementação completa de todas as funcionalidades planejadas
2. Melhorias de usabilidade e acessibilidade
3. Desenvolvimento de um backend mais robusto para sincronização de dados
4. Expansão para incluir funcionalidades adicionais, como biblioteca digital e apoio pedagógico
5. Realização de testes com usuários reais em ambiente escolar

## 7. Referências

1. Documentação do Kivy/KivyMD: https://kivy.org/doc/stable/ e https://kivymd.readthedocs.io/
2. SQLite Documentation: https://www.sqlite.org/docs.html
3. Material Design Guidelines: https://material.io/design
4. Nielsen, J. (1994). Usability Engineering. Morgan Kaufmann.
5. Pressman, R. S. (2014). Software Engineering: A Practitioner's Approach. McGraw-Hill Education.

## 8. Anexos

Os seguintes documentos complementam este relatório final e estão disponíveis no repositório do projeto:
1. Documentação completa do projeto
2. Requisitos funcionais e não funcionais
3. Regras de negócio
4. Modelagem de dados
5. Protótipos de interface
6. Código-fonte do protótipo
7. Relatório de testes

## 9. Agradecimentos

Agradecemos à instituição de ensino pela oportunidade de desenvolver este projeto multidisciplinar, que permitiu aplicar os conhecimentos adquiridos ao longo do curso em um contexto prático e relevante. Agradecemos também aos professores e orientadores pelo suporte e direcionamento durante todo o processo de desenvolvimento.
