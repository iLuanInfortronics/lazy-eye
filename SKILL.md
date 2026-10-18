---
name: lazy-eye
description: Use ao criar ou auditar telas, formulários, configuradores, instaladores e fluxos de CLI para reduzir o esforço de entender, pensar, preencher e concluir; em telas, confere simetria e alinhamento. Inclui auditoria profunda e composição opcional com skills de design premium.
---

# Lazy Eye

Enxergue o trabalho que a solução deixará para a pessoa. O objetivo é reduzir o esforço total para chegar ao resultado, incluindo aprender, localizar informações, executar, conferir e corrigir. Numa tela, design e função formam um único fluxo: mudar só a aparência não resolve uma escolha difícil, e adicionar um recurso não resolve uma hierarquia confusa. Menos cliques, por si só, não é melhoria.

Use o **olhar preguiçoso** como teste de usabilidade: uma pessoa sem conhecimento prévio deve conseguir reconhecer o próximo passo, aproveitar dados que o sistema já conhece, escolher entre opções claras e perceber que terminou, sem pesquisar códigos nem interpretar jargão. Isso avalia o esforço imposto pelo produto, não a capacidade da pessoa. Prefira preenchimento confiável e escolhas guiadas à digitação e às decisões desnecessárias; mantenha correção, confirmação e consequências sob controle dela.

## Quando aplicar

Use ao planejar ou revisar um fluxo humano, especialmente uma tela que poderia exigir menos passos, escolhas ou explicações. Também se aplica a instalador, CLI, setup e operação recorrente. No uso comum, proponha só a melhoria principal. Quando o usuário pedir uma análise completa, todas as oportunidades ou uma pesquisa profunda, siga o [modo de auditoria profunda](references/auditoria-profunda.md). Não use como pretexto para ampliar refatorações internas nem para sugerir recursos sem relação com a tarefa.

## Como encontrar o atrito

1. Identifique quem fará a tarefa, o resultado esperado e se o uso será único ou repetido. Se o fluxo já existir, examine-o; num fluxo novo, use apenas os requisitos conhecidos e marque as hipóteses.
2. Percorra mentalmente a primeira execução, uma repetição e a ação seguinte à conclusão. Numa tela, examine juntos o que aparece, a ordem das informações, os controles e o que acontece ao usá-los. Verifique se alguém sem conhecer o sistema entende o próximo passo sem ajuda. Localize onde a pessoa precisará adivinhar, digitar em vez de aproveitar dados ou opções confiáveis, procurar fora do fluxo, repetir trabalho, esperar sem orientação ou recomeçar após um erro.
3. Escolha o atrito com maior combinação de frequência, esforço e chance de erro. Fundamente-o no fluxo observado; se faltar um fato decisivo, formule a sugestão como hipótese e diga o que precisa ser conferido.
4. Percorra a escada abaixo para o atrito encontrado. Separe problemas distintos em vez de empilhar mudanças numa proposta. Compare o trabalho poupado com o custo de aprender, manter e corrigir a solução; confira se o esforço não foi transferido para outro usuário, operador ou suporte. Se o ganho não for claro, não faça sugestão.

Antes de desenhar a solução, escreva o **mapa do trabalho** em uma linha: `ponto de partida → busca ou decisão → ação → confirmação → resultado verificável`. Inclua o caminho de exceção quando ele mudar a recomendação. Compare o mapa atual com o proposto: quais buscas, decisões e retornos à tela desaparecem, e qual trabalho novo surge? Não use contagem de cliques ou uma captura bonita como prova de conclusão.

Em telas, confira a simetria **na renderização**, incluindo os estados e tamanhos de tela relevantes: margens externas, eixos de alinhamento, larguras de elementos equivalentes, espaçamentos e alinhamento entre rótulos e controles. Aponte desvios acidentais que prejudiquem leitura ou previsibilidade; preserve assimetrias intencionais que indiquem hierarquia ou diferenças de função. Não sugira centralizar tudo apenas por estética.

## Escada do esforço poupado

Teste os degraus em ordem. Escolha o primeiro que resolve o objetivo com segurança em todos os caminhos relevantes. Se uma exceção ainda exigir ação humana, combine degraus sem devolver o trabalho desnecessário ao fluxo principal.

1. **Eliminar:** a etapa, campo ou decisão não precisa existir? Remova o pedido ao usuário, preservando regras de negócio e rastreabilidade necessárias.
2. **Resolver pelo contexto:** o sistema já sabe a resposta por uma fonte confiável? Preencha ou execute automaticamente; mantenha a troca autorizada quando houver exceções.
3. **Oferecer um padrão seguro:** não há resposta certa conhecida, mas existe um padrão de baixo risco? Apresente-o de forma clara e editável antes de confirmar; nunca presuma consentimento ou decisão sensível.
4. **Adiar o que é eventual:** a decisão só importa em alguns casos? Mostre-a no momento certo ou agrupe opções avançadas, sem esconder campos obrigatórios ou erros.
5. **Facilitar o inevitável:** se a pessoa ainda precisar agir, torne a entrada ou escolha mais rápida de localizar, executar e corrigir. Escolha o controle pelo volume e contexto, não por moda visual.

Em todos os degraus, preserve validação, feedback, recuperação, acessibilidade e controle sobre consequências. Uma melhoria parcial pode não justificar a complexidade que acrescenta.

## Quando também pedirem design premium

Se o trabalho incluir criar, redesenhar ou polir uma interface, leia [design premium](references/design-premium.md) para combinar a simplificação com direção visual e acabamento. A Lazy Eye continua responsável pelo diagnóstico do esforço e pela sugestão antes de mudanças fora do pedido autorizado. Skills de design disponíveis são colaboradoras condicionais, nunca pré-requisito para a análise nem motivo para ampliar o escopo. Em instaladores e fluxos sem interface visual, siga o método normal.

## Como agir no uso comum

- Apresente no máximo uma sugestão principal por vez: **atrito observado → mudança concreta → esforço poupado → custo ou limite**. Peça aprovação antes de implementar essa melhoria quando ela não fizer parte do pedido já autorizado. Continue partes independentes enquanto aguarda a resposta.
- Se outro caminho alcançar melhor o objetivo do usuário com bem menos esforço, pode sugeri-lo. Não substitua silenciosamente a solução que ele pediu.
- Depois da aprovação, implemente a menor mudança completa, seguindo o padrão do projeto, e verifique o caminho de uso, inclusive erro, teclado e preservação de dados quando aplicável.
- Faça a pessoa chegar ao resultado verificável. Um botão que apenas fecha a tela ou uma mensagem de sucesso antes da operação terminar não encerra a tarefa.
- Se a tarefa pedida já resolve o maior atrito, conclua sem acrescentar uma sugestão ornamental. Não repita a mesma proposta a cada etapa ou resposta.

## Limites

- Automatize trabalho mecânico, não decisões com consequência. Não oculte permissões, custo, destino de dados, alterações de configuração, etapas destrutivas ou riscos de segurança.
- Não troque um controle por outro apenas por preferência visual. Autocomplete ajuda numa lista extensa que exige busca; poucas opções claras podem ser mais fáceis num `select`.
- Ao simplificar uma tela existente, preserve identidade visual e regras de negócio salvo pedido explícito de redesign ou mudança funcional. Quantidade de opções, frequência de uso e contexto determinam se um controle mais sofisticado ajuda.
- Não transfira esforço para outro momento: um padrão rápido que exige correção frequente ou torna erros difíceis de desfazer não é uma melhoria.
- Não trate “usuário preguiçoso” como rótulo da pessoa. Descreva o atrito do produto, não uma falha do usuário.

## Exemplos de julgamento

- **Instalador:** se o usuário teria de pesquisar qual dependência falta, sugira detectá-la e orientar a correção durante a instalação. Confirme requisitos e privilégios antes de propor instalação automática; não acrescente teste de conexão, reparo, atualização ou desinstalação sem necessidade observada.
- **Configuração com muitas prefeituras:** primeiro verifique se o contexto já determina a prefeitura com segurança. Se determinar, proponha preencher ou dispensar a escolha, preservando correção quando necessária. Caso a pessoa ainda precise escolher numa lista longa, sugira busca acessível por nome ou código. Se houver poucas opções, mantenha a escolha simples.
