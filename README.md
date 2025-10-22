# tft
Tutorial de Fluxo de Trabalho

prompt
Considere esse cenário
eu, Radames, tenho um repositorio git chamado projetoBeta
é o repositório com a branch main
Há joao e maria são desenvolvedores/programadores que vão colaborar nesse projeto

quero que funcione assim:
joao escolhe uma tarefa para desenvolver, ele cria uma branch do repositório main.
por exemplo, branch crudPessoa
Maria faz outra branch, crudPedido
quando eles concluirem, fazem um pull request para mim, se eu aprovar eu faço o merge
Organize um tutoria simples em formato markdown para eu padronizar o trabalho de todos.
Quero comandos git para terminal
Dê exemplos do fluxo de trabalho


Tutorial de Fluxo de Trabalho Git (Feature Branch Workflow)Este documento padroniza o uso do Git para desenvolvimento no repositório projetoBeta.Repositório: projetoBetaBranch principal: mainColaboradores: João e Maria (Desenvolvedores), Radamés (Mantenedor/Aprovador)1. Configuração Inicial (Uma única vez)Todos os colaboradores devem clonar o repositório e configurar o nome de usuário/e-mail (se ainda não o fizeram).Bash# 1. Clonar o repositório
git clone <URL_DO_REPOSITORIO_PROJETOBETA>
cd projetoBeta

# 2. Verificar a branch principal
git branch

# Se ainda não configurou globalmente (opcional, mas recomendado)
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@exemplo.com"
2. Início de uma Nova Tarefa (Desenvolvedores: João e Maria)Antes de começar qualquer nova funcionalidade ou correção, o desenvolvedor deve garantir que a branch main local esteja atualizada e, em seguida, criar uma nova branch de funcionalidade.2.1. Sincronizar com mainBash# 1. Trocar para a branch principal
git checkout main

# 2. Puxar as últimas alterações (garantir que o 'main' está atualizado)
git pull origin main
2.2. Criar a Branch da TarefaO nome da branch deve ser descritivo e, preferencialmente, em letras minúsculas.Exemplo (João): Para a tarefa de CRUD de Pessoas:Bash# 1. Criar e trocar para a nova branch
git checkout -b crudPessoa
# Agora você está na branch 'crudPessoa'
Exemplo (Maria): Para a tarefa de CRUD de Pedidos:Bash# 1. Criar e trocar para a nova branch
git checkout -b crudPedido
# Agora você está na branch 'crudPedido'
3. Desenvolvimento e Commits (Desenvolvedores: João e Maria)À medida que o trabalho avança, o desenvolvedor deve fazer commits frequentes com mensagens claras e objetivas.Bash# 1. Fazer as alterações no código...

# 2. Verificar quais arquivos foram alterados
git status

# 3. Adicionar os arquivos alterados ao 'staging area'
git add . 
# (ou use 'git add nome/do/arquivo' para adicionar seletivamente)

# 4. Fazer o commit com uma mensagem descritiva
git commit -m "feat: Adiciona estrutura inicial do CRUD de Pessoas"
4. Conclusão da Tarefa e Pull Request (Desenvolvedores: João e Maria)Quando a funcionalidade estiver completa, testada e pronta para revisão, o desenvolvedor deve enviar a branch para o repositório remoto e criar um Pull Request (PR).4.1. Enviar a Branch RemotamenteBash# Enviar a branch para o repositório remoto.
# O '-u' (ou --set-upstream) é usado na primeira vez para rastrear a branch remota.
git push -u origin crudPessoa 
4.2. Criar o Pull Request (PR)Ação: O desenvolvedor deve ir para a interface web da plataforma Git (GitHub, GitLab, Bitbucket, etc.).Detalhes:Source Branch (Origem): crudPessoa (ou crudPedido)Target Branch (Destino): mainMensagem: Preencher o template do PR com descrição da tarefa, testes realizados e referências.5. Revisão e Merge (Mantenedor: Radamés)Radamés deve revisar o código no Pull Request.5.1. RevisãoRadamés revisa o código, faz comentários e solicita alterações, se necessário.5.2. Merge (Se Aprovado)Se o código estiver aprovado e todos os testes/verificações automáticas passarem, Radamés realiza o Merge do PR na branch main (geralmente via interface web).Ação: Clicar no botão "Merge" (ou "Squash and Merge", dependendo da política).6. Limpeza (Desenvolvedores: João e Maria)Após o merge, a branch de funcionalidade não é mais necessária. O desenvolvedor deve sincronizar sua branch main local e, opcionalmente, deletar a branch local e remota.6.1. Atualizar a main LocalBash# 1. Trocar para a branch principal
git checkout main

# 2. Puxar as últimas alterações (incluindo o merge do PR)
git pull origin main
6.2. Deletar a Branch de Funcionalidade (Opcional, mas recomendado)Deletar Localmente:Bash# O '-d' é para deletar (funciona se a branch já foi merged)
git branch -d crudPessoa 
Deletar Remotamente (Geralmente a plataforma faz isso, mas se precisar):Bash# Envia o comando de exclusão para o repositório remoto
git push origin --delete crudPessoa 
7. Resumo do Fluxo de Trabalho por TarefaPassoQuemComando PrincipalObjetivoInícioJoão/Mariagit pull origin mainGarantir que a main local esteja atualizada.BranchJoão/Mariagit checkout -b nova-tarefaCriar um ambiente isolado para o desenvolvimento.TrabalhoJoão/Mariagit add . e git commit -m "..."Registrar o progresso com mensagens claras.EnvioJoão/Mariagit push -u origin nova-tarefaEnviar o trabalho para o repositório remoto.RevisãoJoão/Maria(Web) Criar Pull RequestSolicitar revisão e merge.MergeRadamés(Web) Aprovar e MergearIntegrar o código na main.LimpezaJoão/Mariagit pull origin main e git branch -dSincronizar e remover a branch de tarefa.Este fluxo garante isolamento do desenvolvimento, facilita a revisão e mantém a branch main sempre estável.


