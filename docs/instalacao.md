# Instalar e começar, sem precisar programar

Instalar a skill e criar o Brain são duas etapas. Primeiro o agente precisa conseguir ler as instruções da skill; depois você escolhe **onde seu projeto privado vai morar**.

## Opção 1 — Peça ao agente local

Abra Codex ou Claude Code com acesso ao computador e envie o pedido de instalação do README. Ele deve conferir o diretório suportado pela versão, preservar instalações existentes, copiar a pasta inteira e confirmar `SKILL.md`. Não precisa dar senha de GitHub: o repositório é público.

## Opção 2 — Instalação manual no computador

1. Baixe [revo-brain-codex-claude.zip](https://github.com/Revogrowth2/revo-public-skills/releases/latest/download/revo-brain-codex-claude.zip).
2. Extraia. Você deve encontrar uma pasta `revo-brain-codex-claude` com `SKILL.md`, `references`, `assets`, `agents` e `LICENSE`.
3. Copie a pasta inteira para um destino suportado. Não deixe duas pastas com o mesmo nome aninhadas.

| Agente | Apenas no projeto | Para o usuário local |
|---|---|---|
| Codex | `<projeto>/.agents/skills/revo-brain-codex-claude/` | macOS/Linux: `~/.agents/skills/revo-brain-codex-claude/`; Windows nativo: `%USERPROFILE%\.agents\skills\revo-brain-codex-claude\` |
| Claude Code | `<projeto>/.claude/skills/revo-brain-codex-claude/` | macOS/Linux: `~/.claude/skills/revo-brain-codex-claude/`; Windows nativo: `%USERPROFILE%\.claude\skills\revo-brain-codex-claude\` |

`~` significa sua pasta de usuário; `%USERPROFILE%` vale no Explorador/CMD. No PowerShell, use `$env:USERPROFILE`. Diretórios personalizados e versões antigas podem diferir: confira a documentação oficial/descoberta do agente. Em WSL, use a home do Linux e abra o projeto no ambiente correspondente; não presuma que instalar no Windows também instala no WSL.

4. Recarregue a descoberta ou abra uma nova sessão. Peça ao agente para confirmar qual `SKILL.md` ele leu. Nome na lista não comprova configuração do Brain.
5. Use o prompt inicial do README. Para usar ambos, instale a mesma versão nos dois agentes. Atualizações por cópia exigem reaplicar a versão; link compartilhado é opcional avançado e precisa ter destino válido em cada máquina.

## Opção 3 — Navegador ou app sem pasta local

Se o produto permitir importar skills, importe o ZIP pelo mecanismo da conta. Os nomes de menus e disponibilidade variam. Se não permitir, extraia e forneça `SKILL.md`, as referências necessárias **e os modelos pertinentes de `assets/templates/`** como arquivos/instruções do projeto, preservando ou indicando seus caminhos. Para a primeira configuração, forneça a pasta completa se o produto conseguir ler esse formato; caso contrário, anexe os arquivos individualmente. Diga: “Siga este guia como procedimento e confirme quais instruções, referências e modelos você realmente recebeu e consegue ler ou salvar”. Anexar não prova instalação persistente.

No navegador comum, o agente **não consegue ler `C:\...` ou `/Users/...` só porque você citou o caminho**. Use anexos revisados ou um conector autorizado com escopo específico. Veja [o fluxo browser da skill](../skills/revo-brain-codex-claude/references/browser.md). Não envie o cofre, `.env` nem o backup inteiro.

## Instalação pelo catálogo `skills` (opcional)

```sh
npx skills add Revogrowth2/revo-public-skills --skill revo-brain-codex-claude
```

Requer Node/npm e usa instalador de terceiros, não código deste repositório. Leia as opções e escolha o agente/destino correto. Instalação manual funciona sem Node, Python, Git ou terminal.

## Documentação de referência

- [Skills no Codex/ChatGPT](https://learn.chatgpt.com/docs/build-skills)
- [Customização e AGENTS.md](https://learn.chatgpt.com/docs/customization/overview)
- [Skills no Claude Code](https://code.claude.com/docs/en/skills)
- [CLAUDE.md e imports](https://code.claude.com/docs/en/memory)

Confirme sempre comportamento da sua versão. Este método não é uma extensão oficial dos produtos.
