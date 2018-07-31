# Instruções

Este repositório tem por objetivo instruir os alunos de projeto final sobre como deverão realizar sua especificação de requisitos. Toda a documentação do software será deverá ser feita utilizando a linguagem Mark Down, para que ao fim todo o material esteja disponível na página do GitHub do projeto.

Este documento servirá não somente como um exemplo de como os requisitos deverão ser especificados, mas também como referência da linguagem Mark Down e de git.

## Inicializando seu repositório

Primeiramente, baixe seu repositório remoto para sua máquina utilizando a URL fornecida no site do GitHub.

```
git clone https://github.com/cp2-dc-info-projeto-final-2018/exemplo-requisitos.git
```

Entre na pasta criada para seu repositório com o comando

```
cd exemplo-requisitos
```

Feito isso, utilize um editor de texto de sua preferência (pessoalmente gosto do Atom) para criar/editar um arquivo chamado `README.md`, onde você deverá fazer uma breve descrição do seu projeto utilizando a linguagem Mark Down.

## Adicionando ao staging area

O staging area é a área de preparação do seu commit. Para adicionar seu arquivo `README.md` ao staging area utilize o comando

```
git add README.md
```

## Verificando o staging area

Antes de comitar, é sempre aconselhável verificar o que está no staging area, onde todas as alteração a serem comitadas são rastradas. Para verificar seu staging area, utilize o comando

```
git status
```

## Comitando alterações

Salvar as alterações indicadas no staging area é uma operação chamada commit. O commit é como uma fotografia de uma etapa do desenvolvimento do seu código, e uma vez realizado, não poderá ser desfeito. É sempre possível retornar a uma versão anterior de seu código, porém o commit não deixará de fazer parte do histórico de seu projeto. É sempre aconselhável fazer um comentário no commit, para que seja mais fácil identificá-lo futuramente. Além disso, cada commit deve ser uma operação atômica. Por exemplo, vou fazer um commit apenas para realizar a atualização deste tutorial, nesta parte onde explico sobre atomicidade de um commit. Recomendo clicar em commits no GitHub para ver o histórico de alterações. Clicando neste commit, você poderá ver claramente as diferenças dele para versão anterior. Para realizar um commit inserindo um comentário, utilize o comando

```
git commit -m 'adicionando arquivo README.md'
```

## Se identificando no git

Para enviar seus commits para o GitHub, será necessário se identificar.

### Indicando seu nome

```
git config --global user.name 'Ygor Canalli'
```

### Indicando seu e-mail

```
git config --global user.email 'ygor.canalli@gmail.com'
```

## Enviando commits para o repositório remoto

Para enviar seus commits para o repositório remoto, que em nosso caso é o GitHub, realizamos uma operação chamada push. Para isso, utilizamos o comando

```
git push origin master
```

## Buscando atualizações do repositório remoto

Caso você precisa baixar as alterações do repositório remoto para sua máquina, você precisará realizar uma operação chamada pull. Para isso, utilizamos o comando

```
git pull
```

## Trabalhando com branches

A palavra branch significa galho, ou ramo. Utilizamos branches para viabilizar o tabalho paralelo em diferentes modificações. A idéia é isolar do código principal as modificações que são desenvolvidas, até que estejam prontas, para então levá-las para o código principal. Este código principal, como chamamos, na verdade é um branch chamado `master`. Se não especificamos onde o commit será feito, ele vai para o branch `master`.

Para exercitarmos os branches, primeiramente crie um arquivo `requisitos.md` e comite inserindo o título 'Requisitos'. Lembre de utilizar a linguagem Mark Down.

Criaremos dois branches, um para requisitos funcionais e outro para requisitos não funcionais. Desta forma, podemos dividir o trabalho em duas frentes, ambas adicionando conteúdo ao mesmo arquivo, sem que hajam interferências. Ao final, cada branch será unido de volta ao `master`.

Para criar um novo branch utilize o comando

```
git branch rf
```

Para utilizar este branch utilize

```
git checkout rf
```

A partir de agora todas os comits irão para o branch `rf` ao invés do `master`. Adicione um subtítulo 'Requisitos Funcionais' e comite. Agora iremos fazer um push para o repositório remoto, criando um novo branch remoto simultaneamente. Repare que o branch estava apenas em seu repositório local, não no remoto.

```
git push -u origin rf
```

Agora, vá ao site do GitHub para visualizar seu novo branch. Quando você cria um novo branch, ele terá os mesmos arquivos do branch atual. Então, para criar um branch de requisitos não funcionais independente do de requisitos funcionais, voltaremos ao branch `master`


```
git checkout master
```

Agora criaremos um novo branch para requisitos não funcionais. É possível criar um branch e passar a utilizá-lo de uma única vez, com o comando

```
git checkout -b rnf
```

Agora criamos e estamos trabalhando no branch `rnf`. Repare que nele não há o subtítulo de requisitos funcionais. Crie um subtítulo 'Requisitos Não-funcionais' e comite. Agora vamos fazer um push do nosso branch `rnf` para o repositório remoto.

```
git push -u origin rnf
```

A opção `-u` do comando `git push` não apenas cria o branch remoto, mas especifica que toda vez que for feito um push no branch local, ele irá para o branch remoto definido. Assim, nas próximas vezes que estiver fazendo um push a partir do branch local, não será necessário especificar o branch remoto, pois cada branch fica pré-configurado com seu branch remoto.

Agora dividam-se em equipes para criar a especificação de requisitos neste novo arquivo, utilizando a linguagem Mark Down. Cada equipe deverá trabalhar em um dos branches que criamos agora, uma com requisitos funcionais, outra com requisitos não funcionais.


