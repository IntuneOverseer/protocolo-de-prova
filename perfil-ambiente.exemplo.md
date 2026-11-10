# Perfil de ambiente (EXEMPLO FICTÍCIO)

> Este é um modelo. Todos os nomes, domínios e endereços abaixo são inventados (domínios e IPs reservados para documentação).
> O seu perfil real é **seu**: mantenha local, não publique, não cole em chamado e **nunca** coloque senhas, tokens ou chaves aqui.
> Só entram fatos `[declarado]` (você disse) ou `[provado]` (um comando mostrou). Nada de suposição.

## Execução

- `[declarado]` Estação administrativa: `estacao-admin-01` (produção, uso diário).
- `[provado]` Shell principal: PowerShell 7.x (confirmado com `$PSVersionTable`).
- `[declarado]` Conta administrativa: `admin.exemplo@example.com`.
- `[declarado]` Privilégios: administrador local na estação; funções administrativas conforme a tarefa.

## Servidores e camadas

| Função | Equipamento | Shell | Uso | Observação |
|---|---|---|---|---|
| Diretório (leitura) | `dc-leitura-01.example.com` | Windows PowerShell 5.1 | Coleta de evidências, sem gravação | `[declarado]` |
| Diretório (gravação) | `dc-gravacao-01.example.com` | Windows PowerShell 5.1 | Alterações, com delegação | `[declarado]`; validar token antes de alterar |
| Servidor de atualização | `srv-update-01.example.com` | Windows PowerShell 5.1 | Leitura ou alteração, declarar sempre | `[declarado]` |

## Laboratório (Módulo ER e Gate de Lab)

- `[declarado]` Laboratório Linux: `lab-linux-01` (VM, com snapshot).
- `[declarado]` Laboratório Windows: `lab-win-01` (VM, com snapshot).
- `[declarado]` Dispositivo móvel de teste: `tablet-teste-01`.
- `[declarado]` Rede do laboratório isolada da produção.

## Restrições e políticas

- `[declarado]` Política de execução `AllSigned` na estação administrativa: scripts precisam ser assinados.
- `[declarado]` Código da organização não pode ser enviado a serviços externos sem aval.
- `[declarado]` Projetos pessoais ficam totalmente separados do ambiente da organização.

## Preferências de trabalho

- `[declarado]` Saída dos comandos salva em arquivo de texto e aberta no Bloco de Notas quando não dá para copiar e colar.
- `[declarado]` Arquivos enviados pelo assistente vão para `C:\Users\exemplo\Downloads`.

## Mecanismos mapeados neste ambiente (cresce com o uso)

- `[provado]` Exemplo: o Windows PowerShell 5.1 bloqueia o módulo temporário de um serviço de nuvem por causa do `AllSigned`; o PowerShell 7 resolve sem mexer na política. *(Evidência: saída do erro de assinatura e execução bem-sucedida no PowerShell 7.)*

## Como o assistente usa este arquivo

1. Lê o perfil no início da sessão (ou você cola o conteúdo).
2. Confirma com você apenas o que estiver desatualizado ou faltando.
3. Propõe **acrescentar** fatos novos, mostrando exatamente o que gravaria. Você aprova.
4. Se a evidência de agora contrariar o perfil, vale a evidência e o perfil é corrigido.
