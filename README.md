# pratica-git
Repositórios para a prática de comandos git


~~~bash
git commit --allow-empty
~~~
o parametro `-a` adiciona todos os arquivos modificados e naõ ignorados ao commit atual.

~~~bash
git checkout -b novoBranch
git switch -c novoBranch
~~~

o parametro `-b`alterna para `novoBranch` criando o branch, o mesmo acontece com o comando `git wsitch`com o parametro `c`.

~~~bash
git branch -DnomeBranch
git push --delete origin nomeBranch
~~~

Para apagar um branch é preciso primeiro apagá-lo

~~~bash
git log --graph --oneline
~~~

### Rebase interativo

Para alterar o autor de um commit, você pode utilizar o rebase 
interativo e o comando `commit --amend`.

**Antes, porém**, verifique se o editor de mensagens do commit está
 configurado para o editor do próprio

~~~bash
git rebase -i <referenciamento>
~~~
A referência do commit deve ser sempre para o commit anterior ao
 commit que deve ser alterado.

No editor de commits, altere a instrução do commit desejando de `pick`
 para `edit`. Em seguida grave e feche o editor.

O rebase fará uma pausa para que você altere as informações do autor.

~~~bash
git commit--amend --reset-autor --no-edit
~~~

caso você queira especificar o autor,utilize a flag 
`--author='Nome do Autor <email@autor>`, nesse exatoformato.

caso seu commit seja vazio, acrescente ainda a flag `--allow-empty`.

Após o reparo do commit, continue o processo de rebase com o comando
 abaixo.

~~~bash
git rebase --continue
~~~

Finalmente, **confira o novohistórico localmente** e envie ao repositório remoto **forçadamente**.