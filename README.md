# Protocolo de Prova

Um protocolo para assistentes de IA (e para pessoas) conduzirem **diagnóstico de problemas complexos**, **fechamento de chamados** e **engenharia reversa / desenvolvimento de software** com uma regra simples:

> **Sem prova não avança. Sem contraprova não fecha.**

*Status: rascunho 0.1. Versão em inglês: a fazer.*

> **Aviso importante / Important notice**
>
> **PT:** todos os nomes de empresas, servidores, dominios, contas e situacoes que aparecem nestes arquivos sao **ficticios** e servem apenas de exemplo. Nenhum dado real de organizacao ou de pessoa esta aqui.
> O assistente aprende o seu ambiente **com o protocolo e com o operador**: nada avanca e nada fecha sem que o operador envie a saida da **prova** e da **contraprova**. Prova + contraprova = verdade comprovada nas condicoes testadas.
>
> **EN:** every company, server, domain, account and scenario name in these files is **fictional** and used only as an example. No real organization or personal data is included.
> The assistant learns your environment **from the protocol and from the operator**: nothing advances and nothing closes until the operator sends the output of the **proof** and of the **counter-proof**. Proof + counter-proof = truth established under the tested conditions.

## O problema que ele resolve

Em problemas complexos, o erro mais caro é tratar uma afirmação como verdade: o sistema diz "serviço rodando", o assistente conclui por palpite, o chamado fecha sem a causa. O protocolo troca isso por **portões**: o caso só avança quando a prova do portão anterior existe.

## Como nasceu o método

Nasceu de um erro real: operador e assistente de IA foram enganados por uma dedução que não foi testada. Um teste feito por um caminho diferente do caminho real da falha parecia provar uma coisa, mas a causa estava em outra camada, escondida por uma mensagem de erro genérica. A dedução foi tratada como verdade sem contraprova.

Dessa lição saíram as bases do método: testar somente na trilha exata da falha, no mesmo contexto; pedido do operador exige teste objetivo; níveis de escalonamento (N1, N2, N3); um registro de mecanismos de mascaramento; e rollback executável antes de alterar.

A ideia central não é "aumentar a taxa de acerto". É **impedir que uma hipótese errada seja fechada como verdade antes de pagar o preço da contraprova**, e fazer com que a verdade seja sustentada por prova, não por quem a afirma: o sistema, o operador ou a IA.

O caso é descrito de forma genérica: nenhuma organização, sistema ou pessoa é identificada.

*Autoria: `KaLeK`, com apoio de um assistente de IA na redação e nos refinamentos.*

## O que tem aqui

| Arquivo | O que é |
|---|---|
| `PROTOCOLO-DE-PROVA.md` | O protocolo completo (é o arquivo que você cola nas instruções do assistente) |
| `perfil-ambiente.exemplo.md` | Modelo **fictício** de perfil de ambiente |
| `README.md` | Este arquivo |

## Como usar

1. Cole o conteúdo de `PROTOCOLO-DE-PROVA.md` nas instruções do seu assistente (projeto, prompt de sistema, `CLAUDE.md`, `AGENTS.md` ou equivalente).
2. Comece o problema normalmente. O assistente vai perguntar o **contexto** (onde roda, shell, usuário, privilégio, leitura ou alteração) e só avançar quando tiver a evidência pedida.
3. Execute os comandos **você mesmo** e devolva a saída **completa**. O assistente não executa nada em produção.
4. Feche o caso com a nota formal. O status só é RESOLVIDO com causa provada e contraprova.

## Como ele aprende o seu ambiente

O protocolo não traz nenhum dado de ambiente. O assistente aprende **com você**: pergunta o que falta, marca cada fato como `[declarado]` ou `[provado]` e, se a plataforma tiver memória ou arquivos, **propõe** gravar um perfil local (veja `perfil-ambiente.exemplo.md`). Você aprova o que entra. Sem memória, você cola o perfil no início da sessão.

**Nunca** coloque senhas, tokens ou chaves no perfil nem nas evidências.

## O que ele não faz

- Não executa comandos em produção.
- Não substitui autorização, política da sua organização nem julgamento técnico.
- Não garante o resultado: um assistente de IA pode errar, e por isso existem contraprova, rollback e o Gate de Lab.
- Não afirma ser "o melhor". É um método; a utilidade deve ser medida em casos reais.

## Contribuindo

Sugestões de novos **mecanismos de mascaramento** (comportamentos enganosos reais, com prova) são bem-vindas. Não inclua dados de nenhuma organização.

## Licença

MIT (veja o arquivo LICENSE). Autoria: `KaLeK`.
