# Testar, recuperar e manter

## Teste de aceite, sem dados reais

Use uma tarefa fictícia: “Preparar uma página de demonstração; texto aprovado; design pendente; publicação não autorizada”. Não execute publicação, e-mail ou integração para testar memória.

1. Agente A lê o contexto, registra a frente e salva estado revisão 1 com um marcador fictício identificável e o próximo passo.
2. Verifique arquivo persistido/revisão. No browser, baixe e atualize a fonte mestre; texto no chat não conta como gravação.
3. Abra agente B na mesma pasta ou forneça o pacote revisado. Diga apenas para retomar a frente. Ele deve recuperar tarefa, aprovação, pendência e limite, citar revisão e propor/seguir o próximo passo pertinente.
4. B registra um marco fictício e revisão 2. A, em nova sessão/contexto, lê a revisão 2 e continua sem pedir a conversa inteira.
5. Repita com outra frente e confira que estados não se misturam. Simule uma versão antiga: o agente deve pedir reconciliação/versão correta, sem sobrescrever a nova.
6. Confirme que `acessos.md` não contém valores secretos e que o pacote anexável exclui cofre, `.env` e dados fora do escopo.

Se B não estiver disponível, faça teste documental e marque troca real pendente. Se só existe macOS, não declarar Windows/WSL testado. Registre produto, versão, capacidades e quais passos foram executados.

## Falhas comuns

| Sintoma | Verificação específica |
|---|---|
| “Não lembro” | Pasta errada, skill não descoberta, instruções não carregadas ou estado não salvo. Peça a leitura dos arquivos, sem importar tudo. |
| Agente lê versão antiga | Snapshot/anexo, sync incompleto, checkout/branch ou arquivo só na nuvem. Confira revisão e artefato real. |
| Claude ignora regras | Confira CLAUDE.md e import, escopo de abertura e versão. No browser, forneça AGENTS explicitamente. |
| Outro agente não encontra skill | Instalação específica do app/usuário/WSL, pasta duplicada ou sessão antiga. Confirme SKILL.md exato. |
| Mudança desapareceu | Arquivo só gerado no chat, fonte duplicada, conflito sync ou escrita concorrente. Pare edição e compare versões. |
| “Tudo sincronizado” sem prova | Teste leitura no destino. Presença local não prova disponibilidade remota. |
| Agente relê tudo e fica caro | Enxugue estado e ponte para fontes específicas; mantenha acervo fora do caminho inicial de leitura. |

## Backup e restauração

Escolha retenção e destino privado separado; criptografe quando houver conteúdo confidencial. Teste restaurar uma cópia fictícia fora da pasta mestre. Verifique se contexto, estado e anexos necessários estão íntegros. Não sobrescreva produção para testar backup. Cofre de credenciais segue a rotina própria do fornecedor, separado do Brain.

## Manutenção

Nos marcos, retire duplicação e atualize fatos confirmados com fonte/data. Arquive estados antigos preservando decisões; não apague projeto por inatividade. Ajuste instruções com falhas demonstradas. Atualização da skill pública não deve sobrescrever regras, contexto ou estado já preenchidos dos usuários. Modelos são pontos de partida, não uma migração automática.
