# Regras de Negócio - EscolApp

Com base na entrevista realizada com o diretor da Escola Municipal Professor Paulo Freire, foram identificadas as seguintes regras de negócio para o sistema simplificado de gestão escolar mobile:

## RN01 - Cálculo de Notas e Aprovação
- A nota mínima para aprovação direta é 6,0
- A média anual é calculada com base nas quatro notas bimestrais
- A frequência mínima exigida para aprovação é de 75% das aulas
- Alunos com média inferior a 6,0 ou frequência inferior a 75% são considerados reprovados

## RN02 - Controle de Acesso
- Professores só podem visualizar e editar informações de suas próprias turmas e disciplinas
- Pais/responsáveis só podem visualizar informações relacionadas aos seus filhos
- Alunos só podem visualizar suas próprias informações
- Direção e coordenação têm acesso a todas as informações do sistema
- Secretaria tem acesso às informações cadastrais de todos os alunos

## RN03 - Comunicados
- Todos os comunicados oficiais devem ser aprovados pela direção antes de serem enviados
- Comunicados podem ser direcionados para toda a escola ou para turmas específicas
- Comunicados devem ser escritos em linguagem simples e direta
- Comunicados importantes devem ficar disponíveis para consulta por pelo menos 30 dias

## RN04 - Registro de Frequência
- A frequência deve ser registrada diariamente pelos professores
- O sistema deve calcular automaticamente a porcentagem de frequência
- Alunos com frequência inferior a 75% devem ser destacados para acompanhamento
- Faltas justificadas com atestado médico devem ser registradas separadamente

## RN05 - Ocorrências Disciplinares
- Ocorrências disciplinares devem ser registradas pelos professores ou coordenação
- Ocorrências graves devem gerar notificação imediata aos pais/responsáveis
- Ocorrências devem ser classificadas por tipo e gravidade
- Alunos com mais de três ocorrências graves devem ser encaminhados para acompanhamento especial

## RN06 - Calendário Escolar
- O calendário escolar deve seguir as diretrizes da Secretaria Municipal de Educação
- Eventos e feriados devem ser cadastrados no início do ano letivo
- Alterações no calendário devem ser comunicadas com pelo menos 3 dias de antecedência
- O calendário deve indicar claramente os períodos de avaliação e recesso escolar

## RN07 - Sincronização Offline
- Dados essenciais devem ser armazenados localmente para acesso offline
- Alterações feitas offline devem ser sincronizadas automaticamente quando houver conexão
- Em caso de conflito de dados, a versão mais recente deve prevalecer
- O sistema deve notificar o usuário sobre o status da sincronização

## RN08 - Boletins e Relatórios
- Boletins devem ser gerados ao final de cada bimestre
- Relatórios de frequência devem ser gerados mensalmente
- Relatórios de alunos com baixo desempenho devem ser gerados bimestralmente
- Todos os relatórios devem seguir o formato padrão da escola
