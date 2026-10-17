# Auditoria profunda de simplificação

Use este modo quando o usuário pedir para investigar uma tela ou tarefa inteira e decidir sobre todas as simplificações encontradas. A regra de uma sugestão do uso comum não se aplica aqui. O resultado é um inventário completo dos atritos relevantes dentro do escopo, sem meta artificial de quantidade.

## Investigar antes de propor

1. Delimite a tarefa que a pessoa quer concluir, quem a executa, de onde ela começa e qual resultado verificável confirma o fim. Considere primeira execução, uso frequente, interrupção e recuperação de erro; confira se a pessoa pode achar que terminou sem ter alcançado o resultado.
2. Examine a interface real quando acessível e o código que determina estados, validação, dados e permissões. Percorra o caminho antes, durante e depois da tela: consultas fora do sistema, cópias, pedidos de ajuda e conferências finais. Inclua outras telas e papéis apenas quando fizerem parte da tarefa. Verifique teclado, tamanhos de tela relevantes, carregamento, vazio, erro e sucesso. Consulte observações de uso, instruções, reclamações ou métricas existentes quando houver; não invente frequência ou dor do usuário.
3. Levante atritos em design **e** função: hierarquia e agrupamento, linguagem, controles, escolhas, dados que poderiam ser preenchidos com segurança, etapas repetidas, espera, feedback, correção e retomada. Para cada atrito, percorra a escada do `SKILL.md`; verifique a causa no fluxo e no código antes de recomendar uma troca de componente ou automação.
4. Verifique o impacto em outros papéis, integrações e dados. Uma simplificação que enfraquece segurança, acessibilidade ou regras de negócio, ou apenas empurra trabalho para suporte, não entra na proposta.

Construa uma matriz curta de cobertura antes de chamar a auditoria de completa: início e fim verificável da tarefa; caminho comum, repetição e exceção relevante; estados de espera, erro e recuperação; fontes de dados e autorização das automações propostas. Marque o que foi observado, inferido ou não se aplica. Essa matriz evita que uma tela redesenhada esconda trabalho deslocado para outra etapa.

Se a tela, o código ou outra evidência essencial não estiver acessível, produza apenas um inventário **preliminar**, indique exatamente a cobertura obtida e peça o material que falta. Continue a investigação possível, mas não chame as hipóteses de auditoria completa nem peça aprovação para implementar qualquer item, pacote ou “tudo” antes de fechar a cobertura.

## Montar o inventário

- Registre cada problema independente uma vez. Una sintomas com a mesma causa, mas não misture causas distintas numa mudança genérica.
- Para cada item acionável, informe **local e evidência**, **trabalho imposto à pessoa ou a outro papel**, **degrau e mudança proposta**, **caminho antes/depois em passos, decisões e consultas externas**, **custo ou risco**, **confiança**, **como verificar** e **o que refutaria o ganho esperado**. O antes/depois deve mostrar trabalho real poupado, sem inventar tempo ou métricas. Distinga achado confirmado por inspeção de hipótese que ainda exige verificação.
- Agrupe os itens por dependência de resultado: o que reduz trabalho para chegar ao fim, o que torna a exceção utilizável e o que confirma que a tarefa terminou. Uma melhoria visual só entra quando ajuda uma dessas funções; não conte mudança cosmética como esforço poupado.
- Ordene por benefício provável e dependências. Conte os itens encontrados; não invente oportunidades para preencher uma lista nem esconda as menores quando forem relevantes para o pedido.
- Diferencie o que pode ser simplificado do que é complexidade necessária. Mudança de identidade visual, regra de negócio, permissão, tratamento de dados ou arquitetura exige destaque próprio; não a esconda num pacote de ajustes de UI.

## Apresentar e decidir

Quando a investigação estiver completa dentro do escopo declarado, apresente a lista em tabela ou grupos curtos, com IDs estáveis e um total. Diga quais itens podem formar um pacote coerente e quais exigem decisão separada. Pergunte se o usuário aprova **todos os itens identificados** ou somente IDs escolhidos; aceite exclusões e ajustes. Não implemente nenhuma simplificação da auditoria antes da resposta. Se o pedido era apenas analisar, encerre com o inventário.

Depois da aprovação, implemente todos os itens aprovados, inclusive os chamadores e estados afetados. Verifique o resultado real da tarefa, o caminho de exceção e se o trabalho não migrou para suporte ou correção posterior. Compare sinais observáveis antes/depois quando houver dados; sem eles, registre a hipótese ainda não comprovada. Não declare que “tudo” foi simplificado se a inspeção teve lacunas ou se algum item aprovado ficou pendente.
