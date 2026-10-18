# Lazy Eye

**Uma skill que olha a tela pela pessoa que só quer terminar a tarefa.**

<picture>
  <source media="(prefers-reduced-motion: reduce)" srcset="./assets/lazy-eye-static.png">
  <img src="./assets/lazy-eye-demo.gif" alt="Diagrama animado em cinco etapas: a Lazy Eye percorre a tarefa inteira, identifica esforço oculto, testa os degraus de simplificação, apresenta a proposta para aprovação e confere o resultado. A versão estática resume as cinco etapas." width="1200">
</picture>

*Uma explicação visual do método da skill. A versão estática reúne as cinco etapas para quem prefere menos movimento.*

Uma tela pode parecer simples e ainda obrigar alguém a procurar um código, repetir uma escolha, consultar o suporte ou descobrir que o botão **Concluído** não concluiu nada. A Lazy Eye olha esse caminho pela pessoa que não conhece o sistema e não quer pensar além do necessário. Ela procura dados que podem vir preenchidos, escolhas mais claras e uma ação final que realmente conclua a tarefa.

Funciona em telas, formulários, configuradores, instaladores, fluxos de CLI e tarefas recorrentes. É uma [Agent Skill](https://agentskills.io/) escrita em português.

## Antes e depois de uma tela

<picture>
  <source media="(prefers-reduced-motion: reduce)" srcset="./assets/lazy-eye-before-after-static.png">
  <img src="./assets/lazy-eye-before-after.gif" alt="Exemplo ilustrativo: antes, uma configuração pede prefeitura e código, expõe opções raras e oferece três botões. Após a proposta da Lazy Eye ser aprovada, a tela usa o município da conta com troca acessível, guarda opções avançadas, oferece uma ação para salvar e confirma o resultado. A animação termina com as duas telas lado a lado." width="1200">
</picture>

*Exemplo fictício de uma proposta aprovada. A animação termina com o antes e o depois lado a lado; o diagrama acima explica o método.*

## Dois modos de trabalho

| Pedido | O que você recebe |
| --- | --- |
| Criar ou melhorar um fluxo | Uma sugestão principal: atrito observado, mudança proposta, esforço poupado e custo ou limite. |
| Auditar tudo o que pode ser simplificado | Um inventário de achados com evidência, risco, confiança, antes/depois e IDs para aprovar todos ou escolher alguns. |

A skill **apresenta a sugestão antes de alterar o fluxo** quando a melhoria está fora do pedido já autorizado. Numa auditoria profunda, só pede aprovação de implementação depois de examinar as evidências necessárias. Se faltarem tela, código ou outros dados essenciais, entrega um inventário preliminar e explica a lacuna.

### O mapa do trabalho

Antes de desenhar a solução, a Lazy Eye registra o caminho até um resultado verificável: ponto de partida → busca ou decisão → ação → confirmação → resultado. Compara o caminho atual com o proposto, incluindo a exceção e o trabalho que poderia migrar para o suporte. A animação mostra esse raciocínio em cinco etapas: investigar, encontrar, simplificar, aprovar e conferir.

Em telas, ela também confere a simetria da interface renderizada: margens, alinhamentos, larguras de elementos equivalentes e ritmo entre espaços. Corrige desvios acidentais sem apagar uma assimetria que ajuda a entender a hierarquia.

### Quando a tela também precisa de design premium

A Lazy Eye decide **o que simplificar**. Se a tarefa incluir criação ou redesign de UI, ela pode combinar esse diagnóstico com o `impeccable` para estruturar, criticar ou polir a interface. Skills de direção visual, movimento e acessibilidade entram somente quando resolvem uma lacuna específica. O resultado é uma única proposta de fluxo e visual, mantendo identidade, regras e aprovação; nenhuma dessas skills é obrigatória para usar a Lazy Eye.

| Papel | Skill, quando disponível |
| --- | --- |
| Encontrar e reduzir o trabalho da pessoa | `lazy-eye` |
| Estruturar, simplificar e polir a interface | `impeccable` |
| Definir uma direção visual própria, se faltar | `design-taste-frontend` |
| Refinar movimento com propósito, se houver | `emil-design-eng` ou `animate` |
| Conferir uma questão específica de acesso | `accessibility` |

## A escada do esforço poupado

Para cada atrito, ela tenta os degraus nesta ordem. Para no primeiro que resolve a tarefa com segurança; caminhos de exceção podem combinar degraus.

| Degrau | Pergunta | Exemplo |
| --- | --- | --- |
| **01 · Eliminar** | Esta etapa precisa existir? | Remover uma confirmação duplicada. |
| **02 · Resolver pelo contexto** | O sistema já conhece a resposta por fonte confiável? | Propor a prefeitura vinculada à conta, com troca autorizada. |
| **03 · Padrão seguro** | Existe uma escolha comum e de baixo risco? | Oferecer um valor inicial claro e editável. |
| **04 · Adiar** | A decisão só importa em alguns casos? | Mostrar opções avançadas quando forem relevantes. |
| **05 · Facilitar** | A ação humana continua necessária? | Usar busca numa lista extensa; manter um `select` para poucas opções claras. |

Validação, acessibilidade, feedback, recuperação de erros e controle sobre consequências permanecem em todos os degraus. A skill não presume consentimento nem automatiza decisões sensíveis.

## Exemplo: instalador que diz “Concluído” cedo demais

**Antes:** instalar → ver “Concluído” → tentar abrir → descobrir dependência ausente → pesquisar uma versão → instalar → repetir → chamar suporte se falhar.

**Proposta:** verificar a dependência e sua compatibilidade; orientar a correção dentro do instalador; mostrar “Concluído” somente quando o aplicativo estiver apto a abrir. Instalar a dependência automaticamente só entra na proposta depois de confirmar origem, versão, licença e privilégios.

Numa auditoria profunda, a Lazy Eye também pergunta: *o que comprovaria o ganho?* e *o que mostraria que a hipótese estava errada?* Sem acesso ao instalador e aos requisitos, isso continua sendo uma proposta preliminar.

## Instalação

Instale globalmente no Codex, Claude Code e Antigravity com a [CLI de Agent Skills](https://github.com/vercel-labs/skills):

```bash
npx --yes skills@1.7.2 add https://github.com/iLuanInfortronics/lazy-eye --skill lazy-eye --global --agent codex claude-code antigravity --yes
```

Reabra a sessão do agente após a instalação. Você também pode copiar `SKILL.md` e `references/` para uma pasta `lazy-eye` no diretório de skills do agente.

### Como pedir

```text
Use a skill lazy-eye e sugira a principal simplificação desta tela antes de mudar o fluxo.
```

```text
Use a skill lazy-eye em modo de auditoria profunda. Examine esta tarefa inteira, liste todas as simplificações relevantes com evidências e traga os IDs para minha aprovação.
```

A seleção automática depende do agente e de quantas skills ele carrega. Mencionar `lazy-eye` explicitamente é o caminho mais previsível.

## Dentro do repositório

- [`SKILL.md`](./SKILL.md): gatilho, escada e limites do uso cotidiano.
- [`references/auditoria-profunda.md`](./references/auditoria-profunda.md): método de investigação, inventário e aprovação.
- [`references/design-premium.md`](./references/design-premium.md): composição opcional com skills de design para interfaces.
- [`assets/`](./assets/): animação do método e exemplo de antes/depois, ambos com alternativa estática para movimento reduzido.

## Licença

MIT. Veja [`LICENSE`](./LICENSE).
