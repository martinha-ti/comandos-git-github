# comandos-git-github
Comandos git github para iniciantes.

# Resumo Git

**[Inicializando](#inicializando)**  
**[Visualizar modificações](#visualizar-modifica%C3%A7%C3%B5es)**  
**[Adicionando e fazendo commit](#adicionando-e-fazendo-commit)**  
**[Trabalhando com remoto](#trabalhando-com-remoto)**  
**[Desfazendo coisas](#desfazendo-coisas)**  
**[Alterando configurações](#alterando-configura%C3%A7%C3%B5es)**  

---

## Inicializando

- Inicializar um repositório git:

```$ git init```

## Visualizar modificações

- Visualizar os arquivos que foram modificados:

```$ git status```

- Visualizar as modifições realizadas:

```$ git diff [--name-only]```

- Visualizar lista dos commits já realizados:

```$ git log [--stat] [--graph] [--author="Autor"] [--decorate]```

- Visualizar árvore de branchs e commits:

```$ git log --graph --pretty=oneline --abbrev-commit```

- Visualizar log resumido dos commits, mostrando quantidade de commits e quais foram os commits:

```$ git shortlog [-sn]```

- Visualizar detalhes de um commit:

```$ git show hash_do_commit```

## Adicionando e fazendo commit

- Adicionar todos os arquivos modificados para serem enviados no commit:

```$ git add .```

- Realizar commit com descrição do que foi modificado:

```$ git commit -m "Descrição das modificações"```

- Realizar commit já adicionando todos os arquivos modificados, que já tenham sido adicionados alguma vez, e enviando a mensagem:

```$ git commit -am "Descrição das modificações"```

## Trabalhando com remoto

- Adicionar um repositório remoto:

```$ git remote add origin https://github.com/davidalves1/gerador-cnpj.git```

- Visualizar branchs locais e remotos:  
 
```git branch [--list] [-a]```

- Enviar as modificações commitadas:

```$ git push origin master```

- Criar tags para versionamento:

```$ git tag -a 1.0.0 -m "Descrição sobre a versão"```  
```$ git push origin master --tags```

- Criar um branch e mudar para ele ao mesmo tempo:

```$ git checkout -b nome_do_branch```

- Enviar o branch para o repositório remoto

```$ git push origin nome-do-branch```

## Desfazendo coisas

- Remover arquivo do monitoramento do Git:  
```$ git rm --cached arquivo``` ou ```$ git rm arquivo #(OBS: CUIDADO, este último comando exclui o arquivo do HD também)```

- Apagar branch ou tag remotos:

```$ git tag -d 1.0.0``` ou ```$ git branch -d iss42```   
```$ git push origin :1.0.0``` ou ```$ git push origin :iss42```

- Remover remoto:

```$ git remote -v``` | Para verificar os remotos existentes  
```$ git remote rm nome_do_remoto```

- Desfazer mudanças antes de adicionar o arquivo modificado:

```$ git checkout nome_do_arquivo```

- Desfazer mudanças após os arquivo ter sido adicionado à fila:

```$ git reset HEAD nome_do_arquivo```  
```$ git checkout nome_do_arquivo```

- Desfazer alterações após ter realizado o commit:

```$ git reset [--soft] [--mixed] [--hard] hash_do_commit_anterior_ao_que_se_quer_excluir```

Onde: 
 - --soft: apaga o commit mas deixa os arquivos na fila para commitar novamente; 
 - --mixed: apaga o commit e retira os arquivos da fila para serem commitados;
 - --hard: apaga o commit e as alterações nos arquivos; 

- Reverter o que foi enviado. Este comando não apaga o commit, ele faz um novo commit desfazendo o que foi feito no commit escolhido. Usado para salvar sua sexta. :)

```$ git revert hash_do_commit_a_ser_revertido```

## Alterando configurações

- Criar um alias para algum comando:

```$ git config --global alias.nome_do_alias comando```

```
# Meus alias pessoais
$ git config --global alias.cm commit
$ git config --global alias.ck checkout
$ git config --global alias.st status
$ git config --global alias.ps push
$ git config --global alias.pl pull
$ git config --global alias.br branch
```

- Alterar nome e e-mail do usuário:

```$ git config --global user.name "Seu Nome"```  
```$ git config --global user.email "seu@email.com"```   

- Visualizar todas as configurações

```$ git config --list```
