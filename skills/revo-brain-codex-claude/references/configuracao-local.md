# Configuração local: passo a passo

## 1. Escolha onde seu projeto mora

Explique as opções e use a pasta já existente quando correta. Exemplos fictícios:

- Windows: `C:\Projetos\meu-projeto`.
- macOS: `~/Projetos/meu-projeto`.
- Linux/WSL: `~/projetos/meu-projeto`.

Pode criar pelo Explorador/Finder sem terminal. Não use Downloads/lixeira/pasta temporária como fonte mestre. Evite a pasta pública onde baixou esta skill. Para equipe, escolha pasta/repositório **privado** com acesso só de quem precisa. Verifique instruções nos diretórios superiores; não entre num diretório com instruções desconhecidas para executá-las cegamente.

Antes de preencher qualquer contexto em checkout Git, confira remoto, visibilidade e o que já é rastreado. **Se o repositório for público ou a visibilidade for desconhecida, mantenha o Brain preenchido fora do checkout, em pasta privada.** Dentro dele podem ficar apenas instruções genéricas de leitura, sem revelar fatos privados ou caminhos pessoais. Não alterar a visibilidade do repositório para instalar esta skill.

Se houver código em repositório privado confirmado e o material estiver autorizado ali, o Brain mínimo pode morar na raiz do projeto. Caso contrário, use pasta privada separada e configure acesso somente ao necessário. Uma ponte aponta para o contexto real; não cria segunda cópia mestre. Exclusões Git locais são opção avançada revisada; não substituem escolher um destino seguro antes de preencher arquivos. O modelo de gitignore é ilustrativo, não torna a pasta privada.

## 2. Monte a estrutura mínima

```text
meu-projeto/
  AGENTS.md
  CLAUDE.md
  contexto.md
  historico.md
  acessos.md
  continuidade/
    principal/
      estado.md
      historico/           # criar quando houver versão anterior
  fontes/                  # criar quando houver material relevante
```

Os modelos estão em `../assets/templates/`. Adapte, não copie sobre arquivo existente. Pastas opcionais só são necessárias quando têm conteúdo. Remova instruções de preenchimento depois de adaptar, conservando “a confirmar” onde faltar evidência.

AGENTS guarda regras e ponte para o contexto, não a conversa inteira. CLAUDE novo pode conter só `@AGENTS.md`, import reconhecido pelo Claude Code; a primeira leitura deve ser verificada. CLAUDE existente pode ter regras válidas: preserve-as, acrescente o import compatível e registre contradições. Não assumir que o import ou AGENTS é automático em chats browser ou outros agentes.

## 3. Preencha sem inventar

Registre o nome do projeto, objetivo, situação, restrições e fontes confirmadas. Organize uma frente `principal`; crie outras apenas se realmente houver trabalhos paralelos, por exemplo `site` e `comercial`. Não misture clientes na mesma pasta.

## 4. Abra a pasta em cada agente

No app/IDE/CLI local, abra a raiz correta do projeto. Dê acesso só ao necessário. Envie: “Leia AGENTS.md, contexto.md e continuidade/principal/estado.md. Confirme a versão/data que leu e continue o próximo passo autorizado”. O agente deve confirmar leitura por conteúdo verificável, não só repetir o caminho.

Se o segundo agente não enxerga o arquivo criado pelo primeiro, confira pasta, usuário, mount/WSL, permissões e sync. Criar outra cópia para contornar isso causa divergência; resolva a fonte mestre antes de retomar escrita.

## 5. Sincronização, Git e Obsidian

- Duas ferramentas na mesma máquina podem compartilhar a mesma pasta; isso não sincroniza chats.
- Entre máquinas, Git privado ou Drive/OneDrive/iCloud/Obsidian Sync são opções, não requisitos. Confira login, pasta, download offline e sincronização concluída. Não escolher assinatura sem autorização.
- Um “vault” Obsidian é uma pasta de notas. Abrir a pasta no Obsidian é opcional; plugins/Sync têm configuração e custos próprios. Não criar vault dentro de vault nem copiar o cofre de senhas para ele.
- Evite dois motores de sync na mesma pasta sem avaliar conflitos. Não sincronize credenciais junto por conveniência. Git privado não é cofre de senhas.
- Se usar Git, confira remoto/visibilidade antes de qualquer push e revise arquivos staged. Não executar `git add .` sem inspeção. `.gitignore` não protege arquivos já rastreados.
- Backup é cópia recuperável/versionada, separada da sincronização; criptografe dados sensíveis e teste restauração. Remoções podem se propagar pelo sync.

Sem escrita disponível? Gere os arquivos para a pessoa salvar e descreva isso como preparado, não instalado/gravado. Depois peça a confirmação necessária para testar a leitura real.
