<h1 align="center">
<br>Commits Semânticos 
</h1>
Commits semânticos é uma especificação para formatar mensagens de commit em projetos de desenvolvimento de software. O objetivo do Commits semânticos é fornecer uma maneira consistente e padronizada de comunicar as alterações feitas no código por meio de commits, facilitando o entendimento e o acompanhamento do histórico de desenvolvimento de um projeto.<br><br>

A prática de usar commits semânticos pode trazer benefícios para o desenvolvimento de software em equipe, pois as mensagens de commit claras e informativas podem ajudar os membros da equipe a entender as mudanças feitas no código e como essas mudanças afetam o projeto como um todo. Além disso, torna mais fácil rastrear o histórico de mudanças e entender como o código evoluiu ao longo do tempo.<br>

## Vantagens 
 - Padroniza a nomenclatura;
 - Melhorar a legibilidade do histórico de versionamento do Git;
 - Aumenta a velocidade na hora de procurar por mudanças específicas no código;
 - Facilita a revisão de código, principalmente visando as manutenções futuras do código;
 - Possibilitar a geração de um CHANGELOG ou de release notes de maneira totalmente automatizada;
 - Incentivar os desenvolvedores a realizarem commits de maneira pensada e específica, sem realizar commits grandes e cheios de mudanças;
 - Possibilita a utilização de ferramentas de automação de commits;
 
 ## Recomendações

- Seja breve e direto: Mensagens de commit semânticas devem ser curtas e diretas, para que outros desenvolvedores possam entender rapidamente o que foi alterado.
- Inclua informações detalhadas: Mensagens de commit semânticas devem incluir informações detalhadas sobre o que foi alterado, por que foi alterado e como foi alterado.
- Inclua informações sobre o contexto: Mensagens de commit semânticas também devem incluir informações sobre o contexto do projeto, para que outros desenvolvedores possam entender melhor o que foi alterado.
- Use linguagem apropriada: Mensagens de commit semânticas devem ser escritas em linguagem clara e simples, para que outros desenvolvedores possam entender facilmente o que foi alterado.
 
## Escopo Commits Semânticos:

```
<type>[scope]: <description>

[body]

[footer(s)]
```
## Tipos
Os tipos são a descrição inicial de o que o commit está realizando, sendo obrigatórios e devendo seguir um padrão bem definido.

> `FIX` - Usado quando existem erros de código que estão causando bugs.
> - Exemplo: proteção de uma variável que está gerando um NullPointerException em produção.

> `FEAT` - um commit do tipo FEAT introduz um novo recurso para a base de código (isso se correlaciona com MINOR o controle de versão semântico).
> - Exemplo: adição de um novo endpoint para uma API REST ou um novo consumer para um serviço de mensageria.

> `REFACTOR` - utilizado na realização de uma refatoração que não causará impacto direto no código ou em qualquer lógica/regra de negócio.
> - Exemplo: melhorias de performance revisadas em um code review.

> `STYLE` - utilizado quando são realizadas mudanças no estilo e formatação do código que não irão impactar em nenhuma lógica do código.
> - Exemplo: realizar a indentação de um código.

> `TEST` - usado quando se realizam alterações de qualquer tipo nos testes, seja a adição de novos testes ou a refatoração de testes já existentes.
> - Exemplo: adição de testes de contrato e modificação de testes unitários.

> `DOC` - ideal para quando se adiciona ou modifica alguma documentação no código ou do repositório em questão.
> - Exemplo: adição de documentação sobre o response de uma API ou adição de um README.md.

> `ENV` - utilizado quando se modifica ou adiciona algum arquivo de CI/CD.
> - Exemplo: modificar um comando do Dockerfile ou adicionar um step a um Jenkinsfile.

> `BUILD` - usado quando se realiza alguma modificação em arquivos de build e dependências.
> - Exemplo: adição de dependências do Apache Kafka.

> `CHORE` - Commits do tipo chore indicam atualizações de tarefas de build, configurações de administrador, pacotes... como por exemplo adicionar um pacote no gitignore. (Não inclui alterações em código)

> `CI` - Commits do tipo ci indicam mudanças relacionadas a *integração contínua* (continuous integration).

> `BREAKING-CHANGE` - Funcionalidades que foram retiradas após esse commit.  

## Scopes
- É um prefixo que pode ser adicionado para fornecer mais informações sobre a área do código que foi modificada ou afetada pela alteração. O escopo é importante, pois especifica em qual parte do código foi feita a modificação. 
```
refactor(InvestidorService): modificando regra para cálculo de juros
```

## Body
- O principal objetivo do body é fazer um detalhamento do commit, incluindo informações sobre o porquê das mudanças, os problemas que foram resolvidos, quaisquer impactos nas outras partes do código, etc. Isso pode ser muito útil para outros desenvolvedores que precisam entender as mudanças feitas no código e como elas podem afetar a aplicação como um todo.

```
fix(ProdutoApi): retirando variável do path da API e ajustando loggers

- O path anterior tinha variáveis desnecessárias e não utilizadas por nenhum consumidor

- Os loggers foram adaptados ao novo padrão utilizado
```
## Footer 
- É a ultima parte da mensagem de commit que contém informações adicionais sobre o commit. Ele pode ser usado como uma finalização do commit, informando o encerramento de uma issue ou o pertencimento/associação a uma task.
```
env: mudando parâmetros de timezone da JVM no Dockerfile

- Os parâmetros anteriores estavam causando uma diferença de horários nas operações devido à incompatibilidade de timezones

# Finaliza Task JD-3108
```

## Mudanças na Pratica
<table>
  <thead>
    <tr>
      <th>Com commits semânticos</th>
      <th>Sem commits semânticos</th>
    </tr>
  </thead>
 <tbody>
    <tr>
      <td>refactor(CachorroService): Otimizando busca por cachorros com risco de pulga</td>
      <td>melhorando métodos da service</td>
    </tr>
    <tr>
      <td>fix(CachorroClient): ajustando URL da chamada pro client</td>
      <td>ajustando url do client</td>
    </tr>
    <tr>
      <td>refactor: padronizando logs em todo o serviço</td>
      <td>ajustando logs do serviço</td>
    </tr>
    <tr>
      <td>feat(GatoApi): adicionando endpoint novo para buscar os gatos pelo ID</td>
      <td>adicionando novo endpoint de gatos</td>
    </tr>
    <tr>
      <td>build: adicionando variavel para buscar ambiente no Jenkinsfile</td>
      <td>update Jenkinsfile</td>
    </tr>
    <tr>
      <td>test: adicionando testes de contrato para todos endpoints de gato e cachorro</td>
      <td>adicionando testes</td>
    </tr>
  </tbody>
</table>

## Exemplos Commits
<table>
  <thead>
    <tr>
      <th>Comando Git</th>
      <th>Resultado no GitHub</th>
    </tr>
  </thead>
 <tbody>
    <tr>
      <td>
        <code>git commit -m ":tada: feat: Commit inicial"</code>
      </td>
      <td>🎉feat: Commit inicial</td>
    </tr>
    <tr>
      <td>
        <code>git commit -m ":books: docs: Atualizaçao do README"</code>
      </td>
      <td>📚 docs: Atualizaçao do README</td>
    </tr>
    <tr>
      <td>
        <code>git commit -m ":bug: fix: Loop infinito na linha 50"</code>
      </td>
      <td>🐛 fix: Loop infinito na linha 50</td>
    </tr>
    <tr>
      <td>
        <code>git commit -m ":sparkles: feat: Pagina de login"</code>
      </td>
      <td>✨ feat: Pagina de login</td>
    </tr>
    <tr>
      <td>
        <code>git commit -m ":bricks: ci: Modificaçao no Dockerfile"</code>
      </td>
      <td>🧱 ci: Modificaçao no Dockerfile</td>
    </tr>
    <tr>
      <td>
        <code>git commit -m ":recycle: refactor: Passando para arrow functions"</code>
      </td>
      <td>♻️ refactor: Passando para arrow functions</td>
    </tr>
    <tr>
      <td>
        <code>git commit -m ":zap: perf: Melhoria no tempo de resposta"</code>
      </td>
      <td>⚡ perf: Melhoria no tempo de resposta</td>
    </tr>
    <tr>
      <td>
        <code>git commit -m ":boom: fix: Revertendo mudanças ineficientes"</code>
      </td>
      <td>💥 fix: Revertendo mudanças ineficientes</td>
    </tr>
    <tr>
      <td>
        <code>git commit -m ":lipstick: feat: Estilizaçao CSS do formulario"</code>
      </td>
      <td>💄 feat: Estilizaçao CSS do formulario</td>
    </tr>
    <tr>
      <td>
        <code>git commit -m ":test_tube: test: Criando novo teste"</code>
      </td>
      <td>🧪 test: Criando novo teste</td>
    </tr>
    <tr>
      <td>
        <code>git commit -m ":bulb: docs: Comentários sobre a função LoremIpsum( )"</code>
      </td>
      <td>💡 docs: Comentários sobre a função LoremIpsum( )</td>
    </tr>
    <tr>
      <td>
        <code>git commit -m ":truck: chore(.ENV): Adicionando arquivo .ENV ao .gitignore"</code>
      </td>
      <td>🚚 chore(.ENV): Adicionando arquivo .ENV ao .gitignore</td>
    </tr>
  </tbody>
</table>

## Padrões de emojis

<table>
  <thead>
    <tr>
      <th>Tipo de commit</th>
      <th>Emojis</th>
      <th>Palavra-chave</th>
    </tr>
  </thead>
 <tbody>
    <tr>
      <td>Adicionando um teste</td>
      <td>✅ <code>:white_check_mark:</code></td>
      <td><code>test</code></td>
    </tr>
    <tr>
      <td>Adicionando uma dependência</td>
      <td>➕ <code>:heavy_plus_sign:</code></td>
      <td><code>build</code></td>
    </tr>
    <tr>
      <td>Alterações de revisão de código</td>
      <td>👌 <code>:ok_hand:</code></td>
      <td><code>style</code></td>
    </tr>
    <tr>
      <td>Bugfix</td>
      <td>🐛 <code>:bug:</code></td>
      <td><code>fix</code></td>
    </tr>
    <tr>
      <td>Comentários</td>
      <td>💡 <code>:bulb:</code></td>
      <td><code>docs</code></td>
    </tr>
    <tr>
      <td>Commit inicial</td>
      <td>🎉 <code>:tada:</code></td>
      <td><code>init</code></td>
    </tr>
    <tr>
      <td>Configuração</td>
      <td>🔧 <code>:wrench:</code></td>
      <td><code>chore</code></td>
    </tr>
    <tr>
      <td>Deploy</td>
      <td>🚀 <code>:rocket:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Documentação</td>
      <td>📚 <code>:books:</code></td>
      <td><code>docs</code></td>
    </tr>
    <tr>
      <td>Estilização de interface</td>
      <td>💄 <code>:lipstick:</code></td>
      <td><code>feat</code></td>
    </tr>
    <tr>
      <td>Infraestrutura</td>
      <td>🧱 <code>:bricks:</code></td>
      <td><code>ci</code></td>
    </tr>
    <tr>
      <td>Lista de ideias (tasks)</td>
      <td>🔜 <code> :soon: </code></td>
      <td><code>docs</code></td>
    </tr>
    <tr>
      <td>Mover/Renomear</td>
      <td>🚚 <code>:truck:</code></td>
      <td><code>chore</code></td>
    </tr>
    <tr>
      <td>Novo recurso</td>
      <td>✨ <code>:sparkles:</code></td>
      <td><code>feat</code></td>
    </tr>
    <tr>
      <td>Package.json em JS</td>
      <td>📦 <code>:package:</code></td>
      <td><code>build</code></td>
    </tr>
    <tr>
      <td>Performance</td>
      <td>⚡ <code>:zap:</code></td>
      <td><code>perf</code></td>
    </tr>
    <tr>
        <td>Refatoração</td>
        <td>♻️ <code>:recycle:</code></td>
        <td><code>refactor</code></td>
    </tr>
    <tr>
      <td>Removendo um arquivo</td>
      <td>🔥 <code>:fire:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Removendo uma dependência</td>
      <td>➖ <code>:heavy_minus_sign:</code></td>
      <td><code>build</code></td>
    </tr>
    <tr>
      <td>Responsividade</td>
      <td>📱 <code>:iphone:</code></td>
      <td><code>style</code></td>
    </tr>
    <tr>
      <td>Revertendo mudanças</td>
      <td>💥 <code>:boom:</code></td>
      <td><code>fix</code></td>
    </tr>
    <tr>
      <td>Segurança</td>
      <td>🔒️ <code>:lock:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>SEO</td>
      <td>🔍️ <code>:mag:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Tag de versão</td>
      <td>🔖 <code>:bookmark:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Teste de aprovação</td>
      <td>✔️ <code>:heavy_check_mark:</code></td>
      <td><code>test</code></td>
    </tr>
    <tr>
      <td>Testes</td>
      <td>🧪 <code>:test_tube:</code></td>
      <td><code>test</code></td>
    </tr>
    <tr>
      <td>Texto</td>
      <td>📝 <code>:pencil:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Tipagem</td>
      <td>🏷️ <code>:label:</code></td>
      <td></td>
    </tr>
    <tr>
      <td>Tratamento de erros</td>
      <td>🥅 <code>:goal_net:</code></td>
      <td></td>
    </tr>
  </tbody>
</table>
