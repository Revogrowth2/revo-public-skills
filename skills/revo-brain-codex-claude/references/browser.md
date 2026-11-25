# Navegador, anexos e agentes sem acesso local

## Verifique a capacidade real

Claude/ChatGPT no navegador, agente cloud, Cowork e um app com ferramenta local são superfícies diferentes. Teste leitura/escrita com arquivo fictício e pasta permitida. Um caminho mencionado ou skill instalada não abre o disco. Repositório montado em cloud também não recebe arquivo privado local automaticamente.

## Sem conector autorizado: caminho manual

1. Mantenha a pasta mestre privada no seu computador ou armazenamento escolhido.
2. Prepare um pacote pequeno: `AGENTS.md`, `contexto.md`, `continuidade/<frente>/estado.md` e só as fontes necessárias, revisadas para a conversa. Mantenha nomes/estrutura se o produto aceitar ZIP; caso contrário, anexe arquivos separados com caminho original indicado. Não juntar cofre, `.env`, histórico bruto ou material de outro cliente.
3. Nas instruções do projeto/chat, peça a leitura desses arquivos ao começar e a produção de checkpoint nos marcos/final. Se imports `@...` não forem reconhecidos, forneça AGENTS diretamente.
4. Informe data/revisão do pacote e fonte mestre. O agente deve confirmar o que leu. Arquivos podem ser snapshots; não alegar leitura da versão atual do disco.
5. No final, o agente entrega o estado/contexto atualizado como arquivo baixável se a ferramenta permitir, ou texto pronto para salvar. A pessoa confere a versão atual da pasta antes de substituir. Havendo mudança concorrente, compare e mescle; nunca substituir cegamente.
6. Atualize a pasta mestre e os anexos/instruções usados na próxima conversa. Um arquivo novo na conversa A pode não atualizar a fonte do projeto nem a conversa B. Verifique leitura de um marcador fictício no agente seguinte.

Essa etapa manual é uma limitação de acesso do ambiente; o agente ainda produz a síntese, sem pedir que a pessoa reconte a conversa. Se não há forma de persistir durante a sessão, sinalize “checkpoint preparado; gravação pendente”.

## Com conector/repositório autorizado

Conecte somente a pasta/repositório privado necessário. Confirme conta, permissões, fonte mestre e se a integração lê, grava ou só indexa snapshots. Não instalar MCP/ponte customizada nem abrir pasta pessoal inteira por padrão. Indexação não garante leitura imediata da revisão nova. Faça teste com arquivo fictício e comprove leitura e gravação separadamente.

Em cloud, alterações no checkout não significam commit, push, merge ou download ao computador. Diga em qual camada o estado ficou salvo; cumpra o fluxo autorizado para chegar à fonte mestre. Não enviar contexto privado a repo público para “facilitar integração”.

## Perguntas que evitam perder continuidade

- Qual arquivo/revisão esta conversa realmente recebeu?
- O checkpoint foi só preparado ou gravado na fonte mestre?
- O próximo agente consegue ler essa mesma revisão?
- Há arquivo mais novo ou conflito de edição?

Se faltar informação, conclua só o que pode comprovar. Skill não transfere histórico, autenticação, memória privada ou assinatura entre fornecedores.
