# Credenciais: onde guardar e como o agente trabalha

## 1. Dois tipos de “vault”

**Pasta de conhecimento** (inclusive vault Obsidian): Markdown, contexto e documentos. Não é cofre criptografado por natureza. **Cofre de credenciais**: gerenciador de senhas com criptografia e controle de acesso, ou recurso seguro do sistema. São coisas separadas.

Escolha o gerenciador que a pessoa/equipe já usa. Exemplos de categorias: gerenciador dedicado como Bitwarden/1Password; cofre de arquivo como KeePassXC; credenciais do sistema como Chaves do macOS ou Credential Manager do Windows, conforme a integração. Não presumir que todos guardam/injetam segredos da mesma maneira. Consulte documentação oficial da ferramenta escolhida antes de configurar CLI/compartilhamento.

## 2. Passo a passo para a pessoa

1. Crie/abra seu cofre no aplicativo oficial. Configure senha mestra forte, MFA quando suportado e recuperação segura. A pessoa faz isso diretamente no app, sem informar senha ao agente.
2. Crie um item por serviço e ambiente, por exemplo “Projeto demonstração / homologação / serviço”. Guarde login, senha/token e notas de recuperação no cofre, com acesso mínimo necessário. Não colocar senha em título ou campo público.
3. Compartilhe pelo recurso do gerenciador com as pessoas certas; nunca pelo Markdown público, Issue ou link aberto.
4. Em `acessos.md`, registre somente serviço, ambiente, responsável, referência **não secreta** do item e forma de solicitar acesso. Não incluir URL assinada, token, resposta MFA ou link secreto de recuperação. Se o índice revelar informações privadas, mantenha-o também fora de anexos/repós públicos.
5. Confira backup/recuperação do cofre conforme o fornecedor. Não exporte CSV em texto puro para facilitar a IA. Não anexe `.kdbx`, seed, códigos de recuperação ou arquivo-chave ao chat.

## 3. Uso pelo projeto

Prefira sessão autenticada, conector com escopo ou injeção pelo gerenciador/runtime quando disponíveis. O agente não precisa conhecer a senha para trabalhar com uma conexão autorizada. Peça à pessoa login/autorização na interface quando necessário, sem coletar o segredo no chat.

Se a stack exigir `.env`, o arquivo é configuração local **em texto puro**, não cofre. A fonte do segredo continua no gerenciador. A pessoa injeta/preenche localmente; o agente pode preparar `.env.example` apenas com nomes de variáveis e valores vazios. Ignore `.env` no Git e limite permissões conforme o sistema. Ignore também backups/exportações; isso não impede que um app com acesso amplo leia o arquivo.

Tokens privilegiados, chaves privadas e service-role ficam no servidor/secret store, nunca em bundle frontend ou variáveis públicas. Não rodar comandos que imprimam ambiente inteiro, cat de `.env`, dumps de gerenciador ou tokens em linha de comando/log. Não incluir segredos em histórico do shell, arquivos de contexto, screenshots ou evidências.

## 4. Se já há segredo no contexto

Não repetir o valor. Aponte a localização de forma redigida, recomende revogar/rotacionar na origem e substituir por referência segura. Apagar o arquivo não invalida a chave e `.gitignore` não limpa histórico. Se foi para Git/nuvem/chat, avalie cópias e permissões com o responsável. Limpeza destrutiva de histórico e revogação de acessos precisam do escopo apropriado; não fazer força bruta ou apagar material sem autorização.

## 5. O que a skill não faz

Não cria criptografia própria, não escolhe senha mestra, não guarda credenciais em serviço da REVO e não certifica segurança do computador. Configuração de um cofre externo e permissões do dispositivo deve ser verificada; a skill fornece o procedimento e registra somente referências.
