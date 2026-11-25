# Protocolo de contexto e retomada

## Um arquivo, um papel

| Arquivo | Papel |
|---|---|
| AGENTS.md | Regras curtas, limites e localização dos documentos. |
| CLAUDE.md | Ponte para regras comuns, preservando regras preexistentes compatíveis. |
| contexto.md | Fatos duráveis, definições do projeto, decisões confirmadas com data/fonte. |
| continuidade/<frente>/estado.md | Objetivo atual, progresso, pendências, validações e próximo passo. |
| historico.md | Marcos de trabalho; entradas recentes primeiro, sem chats brutos. |
| fontes/ | Documentos que justificam o contexto, somente quando necessários e autorizados. |
| acessos.md | Onde obter acesso e quem o administra, sem valores secretos. |

## No começo de uma sessão

1. Identifique a raiz mestre e a frente correta. Leia as regras aplicáveis, contexto e estado atual.
2. Verifique data/revisão e origem. Atualidade de arquivo não garante atualidade do fato; procure a fonte datada relevante.
3. Resuma: “Concluído: ...; pendente: ...; próximo passo: ...; limite de autorização: ...”. Continue o que está autorizado, sem pedir resumo manual de tudo.
4. Caso duas frentes ou fontes discordem, exponha a divergência específica e resolva só o necessário. Nunca declare uma data mais nova como verdade se o registro novo apenas repete hipótese.

## Enquanto trabalha e antes de encerrar

O próprio agente prepara o checkpoint profissional após cada marco material, antes de operação longa arriscada e no fechamento. Um alvo útil é até cerca de 5.000 caracteres de estado atual; fatos e evidências extensos ficam nos arquivos referenciados. Não remova decisão essencial para caber no limite.

Estado mínimo: projeto/frente, revisão, data/fuso, agente, objetivo, realizado, decisões, pendências, verificações executadas, limites, próximo passo e fontes. Separe fato observado, relato, hipótese e a confirmar. Decisão permanente vai para o contexto; decisão de uma tarefa pode ficar no estado. Não copie raciocínio interno, credenciais ou conversas brutas.

Estados diferentes: preparado, alterado, testado, aprovado pela pessoa, publicado, verificado no destino. Não marcar etapa seguinte por dedução. Se só houve planejamento, registre planejamento.

## Escrita concorrente

Antes de editar estado/contexto, releia a versão que está em disco. Compare com a que começou a usar (revisão e, se disponível, hash ou diff). Se outro agente alterou, pare a sobrescrita e reconcilie mudanças ou separe frentes; não rebaixe uma conclusão mais recente ao estado antigo. Data ou número de revisão, sozinhos, não são trava de concorrência.

Preserve a versão anterior do estado em `continuidade/<frente>/historico/` com timestamp ISO seguro para nomes Windows (sem `:`). Se duas edições forem simultâneas, prefira um escritor por frente e combine sequência de trabalho; um arquivo de lock manual não é exclusão atômica. Automação robusta pode usar controle de versão, escrita atômica e comparação de hash, mas não é instalada por esta skill.

Faça nova leitura imediatamente antes da gravação. Não sobrescreva arquivo que mudou durante a edição. Em sistemas sem controle atômico, documente esse limite e não prometa prevenção absoluta de conflitos. Nunca descartar conflito de sync ou usar force-push como “solução rápida”.

## Automação e interrupções

Regras em arquivo instruem o agente; não garantem execução de hooks/autosave. Se quiser hooks, avalie suporte da versão e permissões em etapa posterior, usando conteúdo revisado sem segredos. Não instalar daemon, agendamento ou ponte entre contas por padrão. Após interrupção, leia o último checkpoint e confira o estado real dos artefatos antes de repetir comandos com efeitos.

## Exemplo fictício

“Frente site; revisão 3; 2026-01-15. Formulário corrigido em preview; teste de validação aprovado. Publicação não autorizada. Pendente confirmar destino do lead. Próximo passo: verificar a integração em ambiente de teste, sem criar contato real. Fontes: relatório local e diff da alteração.”

O próximo agente retoma esse ponto; não diz que o site está publicado.
