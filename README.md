# REVO Public Skills

**Skills públicas desenvolvidas pela REVO, por Daniel Canton.** Instruções reutilizáveis para trabalhar com agentes de IA com mais organização, continuidade e controle.

## Primeira skill: REVO Brain — Codex e Claude

Você encerrou uma tarefa no Claude e quer continuar no Codex, ou voltou dias depois e precisa saber onde o projeto parou? A **`revo-brain-codex-claude`** orienta a criação de uma memória de trabalho em arquivos: regras, contexto, decisões, estado atual e próximos passos.

O agente guia a configuração, passo a passo, e cria os arquivos quando tem acesso e autorização. Funciona também como guia manual. Não é necessário saber programar. Obsidian é opcional.

**O que ela ajuda a montar:**

- Uma pasta por projeto, com caminhos adequados ao seu computador.
- `AGENTS.md` como fonte de regras e `CLAUDE.md` como ponte para Claude Code.
- Contexto curado e checkpoints por frente de trabalho.
- Um protocolo para o agente salvar marcos e outro agente retomar sem recontar a conversa.
- Um lugar seguro para credenciais, separado da memória e dos anexos enviados à IA.
- Uma rotina de sincronização, backup e conferência, sem confundir esses três estados.
- Um caminho para navegadores que não conseguem ler pastas locais.

**Limite importante:** compartilha o estado registrado do projeto. Não transfere a memória oculta, os chats ou as permissões de um produto para outro. No navegador, sem conector autorizado, é preciso anexar/atualizar os arquivos; instalar uma skill não cria acesso automático ao seu disco. Nenhum agente garante autosave se não puder gravar ou for interrompido antes de salvar.

## Comece aqui

1. [Baixe o ZIP da skill](https://github.com/Revogrowth2/revo-public-skills/releases/latest/download/revo-brain-codex-claude.zip).
2. Escolha seu caminho no [guia de instalação](docs/instalacao.md): Codex, Claude Code, upload de skill ou uso manual no navegador.
3. Depois de instalar, envie:

> Use a skill revo-brain-codex-claude para configurar meu Brain de projeto. Identifique meu ambiente e me guie passo a passo. Quero retomar o mesmo trabalho no Codex, no Claude ou em outro agente. Preserve arquivos existentes e mantenha senhas fora do contexto.

No Codex, você pode chamar **`$revo-brain-codex-claude`**. No Claude Code, **`/revo-brain-codex-claude`**. Em outros ambientes, use o nome da skill e o mecanismo de arquivos/instruções disponível.

### Instalação por um agente com acesso ao computador

Você também pode enviar este pedido:

> Instale somente a skill revo-brain-codex-claude do repositório https://github.com/Revogrowth2/revo-public-skills, pasta skills/revo-brain-codex-claude. Leia as instruções antes de executar qualquer coisa. Preserve versões locais e confirme o caminho instalado. Depois, inicie a configuração guiada do meu projeto.

Se você já usa um instalador compatível com `skills`, o comando é:

```sh
npx skills add Revogrowth2/revo-public-skills --skill revo-brain-codex-claude
```

Esse comando usa um instalador de terceiros e exige Node/npm; ele não é necessário para a instalação manual. Selecione os agentes/destinos oferecidos e confira o resultado. Não executa a configuração do Brain por si só.

## Exemplo de resultado

```text
meu-projeto/
├── AGENTS.md
├── CLAUDE.md
├── contexto.md
├── historico.md
├── acessos.md              # referências ao cofre, nunca senhas
├── continuidade/
│   └── principal/
│       ├── estado.md
│       └── historico/      # versões anteriores, quando existirem
└── fontes/                # material privado do projeto, se necessário
```

As instruções explicam também projetos existentes, múltiplas frentes, Windows/macOS/Linux, WSL, conflitos entre agentes, browser, Drive/OneDrive/Obsidian e credenciais locais. Não instalam plugins, sincronizadores, hooks ou serviços pagos.

## Compatibilidade

| Ambiente | Como funciona |
|---|---|
| Codex local/app/IDE com pasta acessível | Skill + leitura das instruções e arquivos do projeto. |
| Claude Code com pasta acessível | Skill + `CLAUDE.md` importando `AGENTS.md`. |
| Agente remoto com repositório montado | Arquivos presentes no checkout; dados locais não sobem automaticamente. |
| Claude/ChatGPT/outro chat no navegador | Upload de skill se disponível; caso contrário, guia e anexos revisados. Persistência e recursos variam por produto/plano. |
| Outros agentes | Mesma estrutura Markdown; configure a leitura explícita se não reconhecerem `AGENTS.md`. |

Não afirmamos teste de execução em todos os produtos/sistemas. O método é portátil; permissões, instalação e sincronização dependem do ambiente. Faça o teste de troca entre agentes antes de confiar na rotina.

## Privacidade e contribuição

Este repositório contém **somente instruções e modelos genéricos**. Seu Brain preenchido deve ficar fora dele, em pasta/repositório privado. Se o projeto que você desenvolve for público ou tiver visibilidade desconhecida, mantenha o Brain privado fora daquele checkout também. Não envie senhas, dados de clientes, screenshots pessoais ou contextos reais em Issues ou Pull Requests. Leia [SECURITY.md](SECURITY.md).

Encontrou uma lacuna? Abra uma Issue com sistema, produto, versão e exemplo fictício. Melhorias de documentação e relatos de testes são bem-vindos: [CONTRIBUTING.md](CONTRIBUTING.md).

**Autoria:** REVO · Daniel Canton. Projeto independente, sem vínculo oficial com OpenAI ou Anthropic. **Licença:** [MIT](LICENSE).
