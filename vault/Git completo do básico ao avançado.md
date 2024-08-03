Antes de começar a usar o git, é necessário configura-lo, para isso vamos utilizar 2 comandos necessários antes de começar:

```
git config --global user.name "SeuUserAqui"
```

Esse comando serve para você adicionar o nome do seu usuário no git (não precisa ser o mesmo nome do github, até porque git não é a mesma coisa que github)

```
git config --global user.email "SeuEmailAqui"
```

E esse comando serve para configurar o email (Também não é necessário ser o mesmo do git)

Esses dois comandos servem para identificar o usuário que usará o git para criar e realizar mudanças no projeto.

Para listar as configurações feitas no git, basta rodar o comando:

```
git config --list
```

E por fim para criar um novo repositório, basta você entrar na pasta desejada e inicializar o git com o comando:

```
git init -y
```

Uma pasta invisível é criada com o nome ".git" e nela estará listado todos os históricos e configurações do git. E Automaticamente o repositório cria uma branch <b>master</b> que é a padrão

<h1>Antes de mais nada, o que é um repositório?</h1>
Pense que repositório é um local onde você armazenas os seus arquivos, onde dentro dele é possível criar novos arquivos, modificar os arquivos existentes e até mesmo deletar!
Tendo com você os históricos de tudo que é feito com esses arquivos através do git.
Git é um software de versionamento que ajuda a gerenciar os arquivos de um projeto.

<h1>Mãos na massa</h1>
Não mencionei anteriormente, mas já criei um repositório dentro de uma pasta chamada gitRepo, e dentro dela um arquivo de texto chamado "hello.txt"

A partir dela vou rodar o seguinte comando:

```
git status
```

O output será semelhante a este: 

![[Pasted image 20240802221646.png]]
- **Primeira linha: "No ramo master"**  
    Isso significa que estou na ramificação `master`, ou, em outras palavras, na "branch master".
    
- **Segunda linha: "No commits yet"**  
    Isso indica que nenhum arquivo foi comitado ainda. Cada commit tem um identificador único e contém uma mensagem descrevendo a alteração.
    
- **Terceira linha: "Arquivos não monitorados"**  
    Isso mostra que há arquivos no diretório que não estão sendo rastreados pelo Git. No caso, o arquivo `hello` aparece em vermelho, indicando que ele não está sendo monitorado. Para começar a rastrear esse arquivo, você deve usar o comando `git add <arquivo>`.
    
- **Quarta linha: "nada adicionado ao envio mas arquivos não registrados estão presentes"**  
    Isso significa que nenhum arquivo foi adicionado à área de staging (preparado para commit), mas existem arquivos não rastreados no diretório. Use `git add` para registrar esses arquivos e incluí-los no próximo commit.


<h1>Vamos então adicionar o comit</h1>
Para comitar o arquivo "hello.txt" basta rodar o seguinte comando:

```
git add hello.txt
```

ou

```
git add .
```

Este ultimo serve para adicionar ao staged todos os arquivos do repositório!
E uma vez adicionado, todas as modificações feitas a posteriore não serão rastreadas, por isso é importante rodar o `git add` sempre que houver alguma modificação.

Rodando `git status` podemos verificar que o arquivo está sendo "traqueado" e qualquer alteração da mesma será mostrado.
![[Pasted image 20240802223004.png]]

<h1>git cached</h1>

Como a proposta do Git é ser utilizado em conjunto com outras pessoas, pode ser necessário manter um arquivo visível apenas na sua máquina local. Para isso, você pode usar o comando `git rm --cached` para remover um arquivo do índice do Git (área de staging) sem deletá-lo do diretório de trabalho. Isso é útil quando você tem arquivos com conteúdo pessoal ou dados sigilosos que não devem ser visíveis para outras pessoas no repositório remoto.
Por exemplo, criei um arquivo chamado `sensivel.txt` com algumas informações. Após adicionar o arquivo ao Git com o comando `git add sensivel.txt`, posso usar o comando `git rm --cached sensivel.txt` para que o Git deixe de rastrear as informações contidas nesse arquivo. Isso mantém o arquivo no seu diretório de trabalho, mas remove-o do índice do Git (área de staging)."

<h1>git cached -r</h1>

Suponhamos que adicionamos um arquivo ao staging de forma equivocada e queremos removê-lo para que o Git pare de rastreá-lo. Podemos rodar o comando `git rm --cached nomeDoArquivo` para removê-lo do índice do Git (área de staging) sem deletá-lo do diretório de trabalho.

<h1>Git commit</h1>
Um commit no Git é uma operação que registra mudanças no repositório. Cada commit representa uma "instantânea" do seu projeto em um determinado momento. Aqui estão alguns pontos chave sobre commits:

1. **Histórico de Alterações**: Um commit armazena informações sobre quais mudanças foram feitas, quem fez essas mudanças e quando elas foram feitas. Isso permite que você acompanhe o histórico de desenvolvimento do seu projeto.
    
2. **Identificador Único**: Cada commit tem um identificador único (hash), que é um código gerado automaticamente pelo Git. Este hash permite que você se refira a um commit específico.
    
3. **Mensagem de Commit**: Cada commit inclui uma mensagem descritiva fornecida pelo usuário que explica a finalidade das mudanças. Isso ajuda a entender o que foi alterado e por quê.
    
4. **Rastreabilidade**: Commits permitem que você volte a versões anteriores do seu projeto, compare mudanças ao longo do tempo, e identifique quando e por quem uma determinada alteração foi feita.
    
5. **Árvore de Commits**: Commits são organizados em uma estrutura de árvore. Cada commit aponta para um ou mais commits predecessores, permitindo que você veja a progressão das mudanças.
    

Aqui está um exemplo básico de como fazer um commit:


`git add <arquivo> git commit -m "Mensagem descrevendo a alteração"`

- O comando `git add` adiciona mudanças à área de staging (preparação para commit).
- O comando `git commit -m "Mensagem"` cria o commit com uma mensagem descritiva das mudanças.

Commits são fundamentais para o controle de versão, permitindo que você mantenha um registro detalhado e organizado das alterações no seu projeto.
Quando voltamos a rodar o `git status`, mostra-se que não há mais nenhum arquivo a serem commitados.
Se forem realizadas alguma alteração no arquivo commitado, veremos que ao rodar o comando `git status` mostrará que o arquivo foi modificado, e para salvar novas alterações, basta realizar um novo commit que uma nova versão do arquivo será salvada.

<h1>Ciclo de vida de arquivo</h1>

![[Pasted image 20240803003209.png]]

<h1>Stage/unstage</h1>

Quando rodamos o `git add .` estamos enviando o arquivo para o staged, se por acaso seja necessário remove-lo do staged, podemos rodar o comando `git restore --staged nomedoArquivo`


<h1>git diff</h1>

Quando modificamos diversos arquivos sem realizar commits, pode chegar um momento em que já não sabemos exatamente o que foi alterado e o que queremos commitar. Com o comando `git diff`, é possível verificar o conteúdo das mudanças nos arquivos modificados, comparando-os com a última versão comitada. Isso ajuda a identificar o que foi modificado antes de realizar um commit.

<h1>Git log</h1>

Rodando o comando `git log` é possível verificar o histórico de commits realizado no repositório, a saida do comando é semelhante a esse:


![[Pasted image 20240803011527.png]]

Mostra-se o hash do commit, a pessoa em que realizou a data e a mensagem do commit.

<h1>Git log variações</h1>
1. `git log --oneline`: Omite o autor e a data, mostrando-se só o hash do commit e a mensagem
2. `git log -n`: O n representa o número de commit que deseja visualizar, do mais recente ao mais antigo, é possível também utilizar com a variação `--oneline`
3. `git -p` ou `git --patch`: Mostra-se a modificação do que foi alterado entre os commits, pode ser utilizado também em conjunto com os dois comandos acima.
4. `git log --stat`: O comando `git log --stat` no Git mostra o histórico de commits com um resumo das mudanças feitas em cada commit. Ele exibe:

> A. **Informações do Commit**: Inclui o identificador único do commit, o autor, a data e a mensagem descritiva.
> B. **Estatísticas de Arquivos**: Lista de arquivos modificados em cada commit, mostrando quantas linhas foram adicionadas e removidas em cada arquivo.
> C. **Resumo Total**: Um resumo no final de cada commit que indica o número total de arquivos modificados, bem como o total de linhas adicionadas e removidas.
> 
> Este comando é útil para ter uma visão geral das alterações feitas no repositório e entender rapidamente o impacto de cada commit sem precisar ver os detalhes completos de cada modificação.


<h1>Git amend</h1>
Suponhamos que você fez um commit com uma mensagem equivocada e deseja corrigi-la. Nesse caso, rodando o comando `git commit --amend -m 'sua mensagem aqui'`, você pode corrigir a última mensagem do commit. Por debaixo dos panos, o Git irá excluir o último commit e criar um novo com a mensagem corrigida.
Agora, suponhamos que você fez um commit, mas esqueceu de adicionar um arquivo. Com o comando `git commit --amend --no-edit`, você pode adicionar o arquivo esquecido e combinar esse novo commit com o anterior, sem alterar a mensagem do commit original.

<h1>Git checkout</h1>
Imagine que você deseja verificar as alterações entre versões, de forma que o Git reconhecerá o estado de um commit específico. Você pode usar o comando `git checkout "hashDoCommit"`, que é muito útil quando você deseja ver a aplicação como um todo no momento em que um commit foi criado.
Os arquivos não serão perdidos e, se desejar voltar à versão atual, você pode rodar o comando `git checkout master`, que restaurará a branch principal na sua última versão.
Além disso, o `git checkout` pode ser usado para descartar as últimas modificações feitas em arquivos não indexados (unstaged). Basta rodar o comando `git checkout nomeDoArquivo` para restaurar a versão anterior do arquivo.

<h1>Git clean</h1>

O git clean serve para excluir arquivos não traqueados, rodando o comando 
`git clean -f` .
É útlil quando você deseja fazer a remoção de um arquivo indesejado.

<h1>Git reset</h1>

Suponhamos que na área de trabalho do seu repositório há alterações em diversos arquivos rastreados e várias inserções de arquivos não rastreados, e você decide limpar todas as modificações para retornar ao commit anterior.
Com o comando `git reset --hard`, você restaura os arquivos rastreados para a última versão do commit de uma só vez. Já com o comando `git clean`, você remove todos os arquivos não rastreados.

<h1>git update-index --skip-worktree nomedoarquivo</h1>

O comando `git update-index --skip-worktree nomeDoArquivo` é usado no Git para marcar um arquivo como "skip-worktree". Isso significa que o Git irá ignorar as alterações feitas nesse arquivo na área de trabalho (working directory) durante operações como `git status` e `git diff`.

### Quando Usar `--skip-worktree`

Esse comando é útil em cenários onde você tem um arquivo de configuração ou algum outro arquivo que precisa ser diferente em cada ambiente de desenvolvimento, mas não quer que essas diferenças sejam rastreadas pelo Git.

### Como Funciona

1. **Marcar um Arquivo com `--skip-worktree`**: Quando você marca um arquivo com `--skip-worktree`, o Git deixa de considerar as alterações feitas nesse arquivo na sua área de trabalho. O arquivo permanece no índice, mas futuras modificações não são mais destacadas.
    
    
    `git update-index --skip-worktree nomeDoArquivo`
    
2. **Verificar o Status dos Arquivos `skip-worktree`**: Para ver quais arquivos estão marcados como `skip-worktree`, você pode usar:
    
    
    `git ls-files -v | grep ^S`
    
    Os arquivos marcados com `S` estão com o atributo `skip-worktree`.
    
3. **Remover o Atributo `skip-worktree`**: Se você quiser voltar a rastrear as alterações de um arquivo, remova o atributo `skip-worktree` com:
    
    
    `git update-index --no-skip-worktree nomeDoArquivo`
    

### Exemplo de Uso

Imagine que você tem um arquivo de configuração `config.json` que contém configurações específicas do ambiente de desenvolvimento. Você não quer que as alterações nesse arquivo sejam rastreadas pelo Git.

1. Marque o arquivo para ser ignorado:
    
    
    `git update-index --skip-worktree config.json`
    
2. Faça alterações no `config.json` conforme necessário. O Git não irá mais reportar essas mudanças quando você rodar `git status` ou `git diff`.
    
3. Se precisar voltar a rastrear as mudanças no `config.json`, remova o atributo:
    
    `git update-index --no-skip-worktree config.json`
    

### Considerações Importantes

- **Diferença entre `--skip-worktree` e `.gitignore`**:
    
    - `.gitignore` é usado para ignorar arquivos completamente, evitando que eles sejam adicionados ao repositório.
    - `--skip-worktree` é usado para arquivos que já estão no repositório, mas cujas futuras modificações devem ser ignoradas.
- **Atenção com Mudanças**:
    
    - Alterações nos arquivos marcados como `skip-worktree` não serão rastreadas, o que pode levar a inconsistências se essas alterações forem importantes para o projeto. Use essa opção com cuidado.

O comando `git update-index --skip-worktree` é uma ferramenta poderosa para gerenciar configurações locais e outras variações de arquivos que não devem ser rastreadas pelo Git, mantendo a integridade do repositório principal.


<h1>Git clone</h1>

É possível clonar repositórios Git com o comando `git clone`. Pode-se clonar repositórios locais ou hospedados.

**Exemplo de repositório local:** Se desejar fazer um clone de um projeto na sua máquina local, basta copiar o caminho da pasta a ser clonada.

**Exemplo de repositório web:** Você também pode clonar qualquer repositório hospedado na web. Basta utilizar o comando `git clone https://exemplo.com.br/riquefernandes`.

Clonando o repositório, além dos mesmos arquivos, você também tem o histórico de todas as alterações que foram feitas.
