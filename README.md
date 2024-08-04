<p class="has-line-data" data-line-start="0" data-line-end="1">Antes de começar a usar o git, é necessário configura-lo, para isso vamos utilizar 2 comandos necessários antes de começar:</p>
<pre><code class="has-line-data" data-line-start="3" data-line-end="5">git config --global user.name &quot;SeuUserAqui&quot;
</code></pre>
<p class="has-line-data" data-line-start="6" data-line-end="7">Esse comando serve para você adicionar o nome do seu usuário no git (não precisa ser o mesmo nome do github, até porque git não é a mesma coisa que github)</p>
<pre><code class="has-line-data" data-line-start="9" data-line-end="11">git config --global user.email &quot;SeuEmailAqui&quot;
</code></pre>
<p class="has-line-data" data-line-start="12" data-line-end="13">E esse comando serve para configurar o email (Também não é necessário ser o mesmo do git)</p>
<p class="has-line-data" data-line-start="14" data-line-end="15">Esses dois comandos servem para identificar o usuário que usará o git para criar e realizar mudanças no projeto.</p>
<p class="has-line-data" data-line-start="16" data-line-end="17">Para listar as configurações feitas no git, basta rodar o comando:</p>
<pre><code class="has-line-data" data-line-start="19" data-line-end="21">git config --list
</code></pre>
<p class="has-line-data" data-line-start="22" data-line-end="23">E por fim para criar um novo repositório, basta você entrar na pasta desejada e inicializar o git com o comando:</p>
<pre><code class="has-line-data" data-line-start="25" data-line-end="27">git init -y
</code></pre>
<p class="has-line-data" data-line-start="28" data-line-end="29">Uma pasta invisível é criada com o nome “.git” e nela estará listado todos os históricos e configurações do git. E Automaticamente o repositório cria uma branch &lt;b&gt;master&lt;/b&gt; que é a padrão</p>
<p class="has-line-data" data-line-start="30" data-line-end="34">&lt;h1&gt;Antes de mais nada, o que é um repositório?&lt;/h1&gt;<br>
Pense que repositório é um local onde você armazenas os seus arquivos, onde dentro dele é possível criar novos arquivos, modificar os arquivos existentes e até mesmo deletar!<br>
Tendo com você os históricos de tudo que é feito com esses arquivos através do git.<br>
Git é um software de versionamento que ajuda a gerenciar os arquivos de um projeto.</p>
<p class="has-line-data" data-line-start="35" data-line-end="37">&lt;h1&gt;Mãos na massa&lt;/h1&gt;<br>
Não mencionei anteriormente, mas já criei um repositório dentro de uma pasta chamada gitRepo, e dentro dela um arquivo de texto chamado “hello.txt”</p>
<p class="has-line-data" data-line-start="38" data-line-end="39">A partir dela vou rodar o seguinte comando:</p>
<pre><code class="has-line-data" data-line-start="41" data-line-end="43">git status
</code></pre>
<ul>
<li class="has-line-data" data-line-start="45" data-line-end="48">
<p class="has-line-data" data-line-start="45" data-line-end="47"><strong>Primeira linha: “No ramo master”</strong><br>
Isso significa que estou na ramificação <code>master</code>, ou, em outras palavras, na “branch master”.</p>
</li>
<li class="has-line-data" data-line-start="48" data-line-end="51">
<p class="has-line-data" data-line-start="48" data-line-end="50"><strong>Segunda linha: “No commits yet”</strong><br>
Isso indica que nenhum arquivo foi comitado ainda. Cada commit tem um identificador único e contém uma mensagem descrevendo a alteração.</p>
</li>
<li class="has-line-data" data-line-start="51" data-line-end="54">
<p class="has-line-data" data-line-start="51" data-line-end="53"><strong>Terceira linha: “Arquivos não monitorados”</strong><br>
Isso mostra que há arquivos no diretório que não estão sendo rastreados pelo Git. No caso, o arquivo <code>hello</code> aparece em vermelho, indicando que ele não está sendo monitorado. Para começar a rastrear esse arquivo, você deve usar o comando <code>git add &lt;arquivo&gt;</code>.</p>
</li>
<li class="has-line-data" data-line-start="54" data-line-end="56">
<p class="has-line-data" data-line-start="54" data-line-end="56"><strong>Quarta linha: “nada adicionado ao envio mas arquivos não registrados estão presentes”</strong><br>
Isso significa que nenhum arquivo foi adicionado à área de staging (preparado para commit), mas existem arquivos não rastreados no diretório. Use <code>git add</code> para registrar esses arquivos e incluí-los no próximo commit.</p>
</li>
</ul>
<p class="has-line-data" data-line-start="58" data-line-end="60">&lt;h1&gt;Vamos então adicionar o comit&lt;/h1&gt;<br>
Para comitar o arquivo “hello.txt” basta rodar o seguinte comando:</p>
<pre><code class="has-line-data" data-line-start="62" data-line-end="64">git add hello.txt
</code></pre>
<p class="has-line-data" data-line-start="65" data-line-end="66">ou</p>
<pre><code class="has-line-data" data-line-start="68" data-line-end="70">git add .
</code></pre>
<p class="has-line-data" data-line-start="71" data-line-end="73">Este ultimo serve para adicionar ao staged todos os arquivos do repositório!<br>
E uma vez adicionado, todas as modificações feitas a posteriore não serão rastreadas, por isso é importante rodar o <code>git add</code> sempre que houver alguma modificação.</p>
<p class="has-line-data" data-line-start="74" data-line-end="75">Rodando <code>git status</code> podemos verificar que o arquivo está sendo “traqueado” e qualquer alteração da mesma será mostrado.</p>
<p class="has-line-data" data-line-start="77" data-line-end="78">&lt;h1&gt;git cached&lt;/h1&gt;</p>
<p class="has-line-data" data-line-start="79" data-line-end="81">Como a proposta do Git é ser utilizado em conjunto com outras pessoas, pode ser necessário manter um arquivo visível apenas na sua máquina local. Para isso, você pode usar o comando <code>git rm --cached</code> para remover um arquivo do índice do Git (área de staging) sem deletá-lo do diretório de trabalho. Isso é útil quando você tem arquivos com conteúdo pessoal ou dados sigilosos que não devem ser visíveis para outras pessoas no repositório remoto.<br>
Por exemplo, criei um arquivo chamado <code>sensivel.txt</code> com algumas informações. Após adicionar o arquivo ao Git com o comando <code>git add sensivel.txt</code>, posso usar o comando <code>git rm --cached sensivel.txt</code> para que o Git deixe de rastrear as informações contidas nesse arquivo. Isso mantém o arquivo no seu diretório de trabalho, mas remove-o do índice do Git (área de staging).&quot;</p>
<p class="has-line-data" data-line-start="82" data-line-end="83">&lt;h1&gt;git cached -r&lt;/h1&gt;</p>
<p class="has-line-data" data-line-start="84" data-line-end="85">Suponhamos que adicionamos um arquivo ao staging de forma equivocada e queremos removê-lo para que o Git pare de rastreá-lo. Podemos rodar o comando <code>git rm --cached nomeDoArquivo</code> para removê-lo do índice do Git (área de staging) sem deletá-lo do diretório de trabalho.</p>
<p class="has-line-data" data-line-start="86" data-line-end="88">&lt;h1&gt;Git commit&lt;/h1&gt;<br>
Um commit no Git é uma operação que registra mudanças no repositório. Cada commit representa uma “instantânea” do seu projeto em um determinado momento. Aqui estão alguns pontos chave sobre commits:</p>
<ol>
<li class="has-line-data" data-line-start="89" data-line-end="91">
<p class="has-line-data" data-line-start="89" data-line-end="90"><strong>Histórico de Alterações</strong>: Um commit armazena informações sobre quais mudanças foram feitas, quem fez essas mudanças e quando elas foram feitas. Isso permite que você acompanhe o histórico de desenvolvimento do seu projeto.</p>
</li>
<li class="has-line-data" data-line-start="91" data-line-end="93">
<p class="has-line-data" data-line-start="91" data-line-end="92"><strong>Identificador Único</strong>: Cada commit tem um identificador único (hash), que é um código gerado automaticamente pelo Git. Este hash permite que você se refira a um commit específico.</p>
</li>
<li class="has-line-data" data-line-start="93" data-line-end="95">
<p class="has-line-data" data-line-start="93" data-line-end="94"><strong>Mensagem de Commit</strong>: Cada commit inclui uma mensagem descritiva fornecida pelo usuário que explica a finalidade das mudanças. Isso ajuda a entender o que foi alterado e por quê.</p>
</li>
<li class="has-line-data" data-line-start="95" data-line-end="97">
<p class="has-line-data" data-line-start="95" data-line-end="96"><strong>Rastreabilidade</strong>: Commits permitem que você volte a versões anteriores do seu projeto, compare mudanças ao longo do tempo, e identifique quando e por quem uma determinada alteração foi feita.</p>
</li>
<li class="has-line-data" data-line-start="97" data-line-end="98">
<p class="has-line-data" data-line-start="97" data-line-end="98"><strong>Árvore de Commits</strong>: Commits são organizados em uma estrutura de árvore. Cada commit aponta para um ou mais commits predecessores, permitindo que você veja a progressão das mudanças.</p>
</li>
</ol>
<p class="has-line-data" data-line-start="100" data-line-end="101">Aqui está um exemplo básico de como fazer um commit:</p>
<p class="has-line-data" data-line-start="103" data-line-end="104"><code>git add &lt;arquivo&gt; git commit -m &quot;Mensagem descrevendo a alteração&quot;</code></p>
<ul>
<li class="has-line-data" data-line-start="105" data-line-end="106">O comando <code>git add</code> adiciona mudanças à área de staging (preparação para commit).</li>
<li class="has-line-data" data-line-start="106" data-line-end="108">O comando <code>git commit -m &quot;Mensagem&quot;</code> cria o commit com uma mensagem descritiva das mudanças.</li>
</ul>
<p class="has-line-data" data-line-start="108" data-line-end="111">Commits são fundamentais para o controle de versão, permitindo que você mantenha um registro detalhado e organizado das alterações no seu projeto.<br>
Quando voltamos a rodar o <code>git status</code>, mostra-se que não há mais nenhum arquivo a serem commitados.<br>
Se forem realizadas alguma alteração no arquivo commitado, veremos que ao rodar o comando <code>git status</code> mostrará que o arquivo foi modificado, e para salvar novas alterações, basta realizar um novo commit que uma nova versão do arquivo será salvada.</p>
<p class="has-line-data" data-line-start="112" data-line-end="113">&lt;h1&gt;Stage/unstage&lt;/h1&gt;</p>
<p class="has-line-data" data-line-start="114" data-line-end="115">Quando rodamos o <code>git add .</code> estamos enviando o arquivo para o staged, se por acaso seja necessário remove-lo do staged, podemos rodar o comando <code>git restore --staged nomedoArquivo</code></p>
<p class="has-line-data" data-line-start="116" data-line-end="117">&lt;h1&gt;git diff&lt;/h1&gt;</p>
<p class="has-line-data" data-line-start="118" data-line-end="119">Quando modificamos diversos arquivos sem realizar commits, pode chegar um momento em que já não sabemos exatamente o que foi alterado e o que queremos commitar. Com o comando <code>git diff</code>, é possível verificar o conteúdo das mudanças nos arquivos modificados, comparando-os com a última versão comitada. Isso ajuda a identificar o que foi modificado antes de realizar um commit.</p>
<p class="has-line-data" data-line-start="120" data-line-end="121">&lt;h1&gt;Git log&lt;/h1&gt;</p>
<p class="has-line-data" data-line-start="122" data-line-end="124">Rodando o comando <code>git log</code> é possível verificar o histórico de commits realizado no repositório<br>
Mostra-se o hash do commit, a pessoa em que realizou a data e a mensagem do commit.</p>
<p class="has-line-data" data-line-start="125" data-line-end="126">&lt;h1&gt;Git log variações&lt;/h1&gt;</p>
<ol>
<li class="has-line-data" data-line-start="126" data-line-end="127"><code>git log --oneline</code>: Omite o autor e a data, mostrando-se só o hash do commit e a mensagem</li>
<li class="has-line-data" data-line-start="127" data-line-end="128"><code>git log -n</code>: O n representa o número de commit que deseja visualizar, do mais recente ao mais antigo, é possível também utilizar com a variação <code>--oneline</code></li>
<li class="has-line-data" data-line-start="128" data-line-end="129"><code>git -p</code> ou <code>git --patch</code>: Mostra-se a modificação do que foi alterado entre os commits, pode ser utilizado também em conjunto com os dois comandos acima.</li>
<li class="has-line-data" data-line-start="129" data-line-end="131"><code>git log --stat</code>: O comando <code>git log --stat</code> no Git mostra o histórico de commits com um resumo das mudanças feitas em cada commit. Ele exibe:</li>
</ol>
<blockquote>
<p class="has-line-data" data-line-start="131" data-line-end="134">A. <strong>Informações do Commit</strong>: Inclui o identificador único do commit, o autor, a data e a mensagem descritiva.<br>
B. <strong>Estatísticas de Arquivos</strong>: Lista de arquivos modificados em cada commit, mostrando quantas linhas foram adicionadas e removidas em cada arquivo.<br>
C. <strong>Resumo Total</strong>: Um resumo no final de cada commit que indica o número total de arquivos modificados, bem como o total de linhas adicionadas e removidas.</p>
<p class="has-line-data" data-line-start="135" data-line-end="136">Este comando é útil para ter uma visão geral das alterações feitas no repositório e entender rapidamente o impacto de cada commit sem precisar ver os detalhes completos de cada modificação.</p>
</blockquote>
<p class="has-line-data" data-line-start="138" data-line-end="141">&lt;h1&gt;Git amend&lt;/h1&gt;<br>
Suponhamos que você fez um commit com uma mensagem equivocada e deseja corrigi-la. Nesse caso, rodando o comando <code>git commit --amend -m 'sua mensagem aqui'</code>, você pode corrigir a última mensagem do commit. Por debaixo dos panos, o Git irá excluir o último commit e criar um novo com a mensagem corrigida.<br>
Agora, suponhamos que você fez um commit, mas esqueceu de adicionar um arquivo. Com o comando <code>git commit --amend --no-edit</code>, você pode adicionar o arquivo esquecido e combinar esse novo commit com o anterior, sem alterar a mensagem do commit original.</p>
<p class="has-line-data" data-line-start="142" data-line-end="147">&lt;h1&gt;Git checkout&lt;/h1&gt;<br>
Imagine que você deseja verificar as alterações entre versões, de forma que o Git reconhecerá o estado de um commit específico. Você pode usar o comando <code>git checkout &quot;hashDoCommit&quot;</code>, que é muito útil quando você deseja ver a aplicação como um todo no momento em que um commit foi criado.<br>
Os arquivos não serão perdidos e, se desejar voltar à versão atual, você pode rodar o comando <code>git checkout master</code>, que restaurará a branch principal na sua última versão.<br>
Além disso, o <code>git checkout</code> pode ser usado para descartar as últimas modificações feitas em arquivos não indexados (unstaged). Basta rodar o comando <code>git checkout nomeDoArquivo</code> para restaurar a versão anterior do arquivo.<br>
Se você tem diversas branch’s e está com arquivos não traqueados e você deseja mudar de ramificação, basta rodar o comando <code>git checkout -f branchEscolhida</code></p>
<p class="has-line-data" data-line-start="148" data-line-end="149">&lt;h1&gt;Git clean&lt;/h1&gt;</p>
<p class="has-line-data" data-line-start="150" data-line-end="153">O git clean serve para excluir arquivos não traqueados, rodando o comando<br>
<code>git clean -f</code> .<br>
É útlil quando você deseja fazer a remoção de um arquivo indesejado.</p>
<p class="has-line-data" data-line-start="154" data-line-end="155">&lt;h1&gt;Git reset&lt;/h1&gt;</p>
<p class="has-line-data" data-line-start="156" data-line-end="158">Suponhamos que na área de trabalho do seu repositório há alterações em diversos arquivos rastreados e várias inserções de arquivos não rastreados, e você decide limpar todas as modificações para retornar ao commit anterior.<br>
Com o comando <code>git reset --hard</code>, você restaura os arquivos rastreados para a última versão do commit de uma só vez. Já com o comando <code>git clean</code>, você remove todos os arquivos não rastreados.</p>
<p class="has-line-data" data-line-start="159" data-line-end="160">&lt;h1&gt;git update-index --skip-worktree nomedoarquivo&lt;/h1&gt;</p>
<p class="has-line-data" data-line-start="161" data-line-end="162">O comando <code>git update-index --skip-worktree nomeDoArquivo</code> é usado no Git para marcar um arquivo como “skip-worktree”. Isso significa que o Git irá ignorar as alterações feitas nesse arquivo na área de trabalho (working directory) durante operações como <code>git status</code> e <code>git diff</code>.</p>
<h3 class="code-line" data-line-start=163 data-line-end=164 ><a id="Quando_Usar_skipworktree_163"></a>Quando Usar <code>--skip-worktree</code></h3>
<p class="has-line-data" data-line-start="165" data-line-end="166">Esse comando é útil em cenários onde você tem um arquivo de configuração ou algum outro arquivo que precisa ser diferente em cada ambiente de desenvolvimento, mas não quer que essas diferenças sejam rastreadas pelo Git.</p>
<h3 class="code-line" data-line-start=167 data-line-end=168 ><a id="Como_Funciona_167"></a>Como Funciona</h3>
<ol>
<li class="has-line-data" data-line-start="169" data-line-end="170"><strong>Marcar um Arquivo com <code>--skip-worktree</code></strong>: Quando você marca um arquivo com <code>--skip-worktree</code>, o Git deixa de considerar as alterações feitas nesse arquivo na sua área de trabalho. O arquivo permanece no índice, mas futuras modificações não são mais destacadas.</li>
</ol>
<pre><code>`git update-index --skip-worktree nomeDoArquivo`
</code></pre>
<ol start="2">
<li class="has-line-data" data-line-start="174" data-line-end="175"><strong>Verificar o Status dos Arquivos <code>skip-worktree</code></strong>: Para ver quais arquivos estão marcados como <code>skip-worktree</code>, você pode usar:</li>
</ol>
<pre><code>`git ls-files -v | grep ^S`

Os arquivos marcados com `S` estão com o atributo `skip-worktree`.
</code></pre>
<ol start="3">
<li class="has-line-data" data-line-start="181" data-line-end="182"><strong>Remover o Atributo <code>skip-worktree</code></strong>: Se você quiser voltar a rastrear as alterações de um arquivo, remova o atributo <code>skip-worktree</code> com:</li>
</ol>
<pre><code>`git update-index --no-skip-worktree nomeDoArquivo`
</code></pre>
<h3 class="code-line" data-line-start=187 data-line-end=188 ><a id="Exemplo_de_Uso_187"></a>Exemplo de Uso</h3>
<p class="has-line-data" data-line-start="189" data-line-end="190">Imagine que você tem um arquivo de configuração <code>config.json</code> que contém configurações específicas do ambiente de desenvolvimento. Você não quer que as alterações nesse arquivo sejam rastreadas pelo Git.</p>
<ol>
<li class="has-line-data" data-line-start="191" data-line-end="192">Marque o arquivo para ser ignorado:</li>
</ol>
<pre><code>`git update-index --skip-worktree config.json`
</code></pre>
<ol start="2">
<li class="has-line-data" data-line-start="196" data-line-end="198">
<p class="has-line-data" data-line-start="196" data-line-end="197">Faça alterações no <code>config.json</code> conforme necessário. O Git não irá mais reportar essas mudanças quando você rodar <code>git status</code> ou <code>git diff</code>.</p>
</li>
<li class="has-line-data" data-line-start="198" data-line-end="201">
<p class="has-line-data" data-line-start="198" data-line-end="199">Se precisar voltar a rastrear as mudanças no <code>config.json</code>, remova o atributo:</p>
<p class="has-line-data" data-line-start="200" data-line-end="201"><code>git update-index --no-skip-worktree config.json</code></p>
</li>
</ol>
<h3 class="code-line" data-line-start=203 data-line-end=204 ><a id="Consideraes_Importantes_203"></a>Considerações Importantes</h3>
<ul>
<li class="has-line-data" data-line-start="205" data-line-end="209">
<p class="has-line-data" data-line-start="205" data-line-end="206"><strong>Diferença entre <code>--skip-worktree</code> e <code>.gitignore</code></strong>:</p>
<ul>
<li class="has-line-data" data-line-start="207" data-line-end="208"><code>.gitignore</code> é usado para ignorar arquivos completamente, evitando que eles sejam adicionados ao repositório.</li>
<li class="has-line-data" data-line-start="208" data-line-end="209"><code>--skip-worktree</code> é usado para arquivos que já estão no repositório, mas cujas futuras modificações devem ser ignoradas.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="209" data-line-end="213">
<p class="has-line-data" data-line-start="209" data-line-end="210"><strong>Atenção com Mudanças</strong>:</p>
<ul>
<li class="has-line-data" data-line-start="211" data-line-end="213">Alterações nos arquivos marcados como <code>skip-worktree</code> não serão rastreadas, o que pode levar a inconsistências se essas alterações forem importantes para o projeto. Use essa opção com cuidado.</li>
</ul>
</li>
</ul>
<p class="has-line-data" data-line-start="213" data-line-end="214">O comando <code>git update-index --skip-worktree</code> é uma ferramenta poderosa para gerenciar configurações locais e outras variações de arquivos que não devem ser rastreadas pelo Git, mantendo a integridade do repositório principal.</p>
<p class="has-line-data" data-line-start="216" data-line-end="217">&lt;h1&gt;Git clone&lt;/h1&gt;</p>
<p class="has-line-data" data-line-start="218" data-line-end="219">É possível clonar repositórios Git com o comando <code>git clone</code>. Pode-se clonar repositórios locais ou hospedados.</p>
<p class="has-line-data" data-line-start="220" data-line-end="221"><strong>Exemplo de repositório local:</strong> Se desejar fazer um clone de um projeto na sua máquina local, basta copiar o caminho da pasta a ser clonada.</p>
<p class="has-line-data" data-line-start="222" data-line-end="223"><strong>Exemplo de repositório web:</strong> Você também pode clonar qualquer repositório hospedado na web. Basta utilizar o comando <code>git clone https://exemplo.com.br/riquefernandes</code>.</p>
<p class="has-line-data" data-line-start="224" data-line-end="225">Clonando o repositório, além dos mesmos arquivos, você também tem o histórico de todas as alterações que foram feitas.</p>