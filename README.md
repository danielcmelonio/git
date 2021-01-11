# Versionando com Git e GitHub

## Você já deve saber, mas vamos repetir.

Git é um versionador de código, um sistema, e para utilizá-lo em seus projetos, não há necessidade alguma de você usar a internet para fazer as operações.

Já o GitHub, ele é um repositório. Ou seja, trata-se de uma hospedagem para códigos versionados pelo sistema GIT. Então, o seu código local, versionado com git, com commits e branchs de várias ordens, pode ser enviado para o GitHub e assim você pode dar acesso público ou não ao seu código. Mas, de toda forma, ele permanece seguro nos registos do site. Você viaja e esquece de levar consigo uma cópia do seu código, mas não há problema, pois se você tiver feito a hospedagem dele no GitHub, tudo o que precisará para acessá-lo será o seu login e senha.

## Começando com o Git

Partindo do pressuposto que você já instalou o git no seu computador, vamos começar pelas configurações primordiais: os dados de quem irá operar o versionador na sua máquina, é você mesmo, não é?

```bash
$ git config --global user.name "Daniel Castro"
$ git config --global user.email "daniel@email.com"
```

Pronto, uma vez que você inseriu seus dados nas configurações, agora você pode listá-las por meio de:

```bash
$ git config --global --list
```

## Ligando o motor do Git

Então, para podermos dirigir, precisamos primeiro de uma avenida, ou mesmo de um autódromo (para aqueles que gostam de viver a aventura da direção no ápice da velocidade e do perigo), então, comecemos por um pasta (no linux chamamos isso de diretório), e essa pasta pode ter o nome que você preferir, a minha vai se chamar _git_, nada pessoal, vamos lá:

```bash
$ mkdir git
$ cd git
```

Agora dentro da pasta git, podemos criar o novo primeiro arquivo:

```bash
$ touch lista.txt
```

Pronto, agora, nosso primeiro arquivo está criado. Então digamos que agora já temos a pista, e também o carro. Mas, falta ligarmos o nosso motor e fazemos jus ao nosso capítulo. Portanto, comecemos:

```bash
$ git init
```

Dessa forma teremos a saída:

_Initialized empty Git repository in ~/git/_

E ela indica que nosso veículo está pronto para ser dirigido em alta velocidade.

## Verificando o painel do veículo (status)

O git assim como um carro, também possui um painel onde você pode verificar qual o status de rastreio dos arquivos do seu projeto. Dessa forma, usamos um comando todo especial para saber se há arquivos novos que ainda não foram rastreados, ou mesmo, se arquivos já declarados sofreram alterações, ou foram eventualmente removidos do diretório.

```bash
$ git status
```

Lembra-se do arquivo _lista.txt_ que criamos? Então, esse comando certamentenos trouxe o nome dele em vermelho, mas calma, isso não significa um erro, significa somente que esse arquivo ainda não foi rastreado pelo versionador, portanto, qualquer modificação que fizermos nesse arquivo, não é de responsabilidade alguma do git ainda. Mas, vamos incluí-lo na lista de rastreio do git com o seguinte comando:

```bash
$ git add lista.txt
```

Se fizermos o ```git status``` outra vez, agora veremos o nome do nosso arquivo em verde, isso significa que ele agora está de fato sendo rastreado pelo git, e que as alterações nele, estão sendo devidamente monitoradas, algo que vai nos ser muito útil a qualquer tempo do ciclo de vida do projeto.

## Precisamos conversar...

A analogia do carro no início me soou interessante, mas apesar de pra início de conversa ela ficar boa. Dar continuidade a ela não será algo muito didático, então, permita-me apresentar-lhe a pílula vermelha, jovem Neo.

O git uma vez iniciado, ele começa a rastrear os arquivos dentro do diretório. E em paralelo a isso é criado também uma dependência (diretório oculto) intitulado _.git_ exatamente para armazenar o controle de versionalmento. Aquele é o repositório que guarda os arquivos que o git precisa para funcionar.

Quando dizemos que os arquivos dentro do diretório são rastreados, isso é algo literal. É como você colocar uma formiga dentro de um recipiente, entretanto, o git só começa a se preocupar com esse arquivo de fato, quando ele é adicionado à área de stage. E seria como dizer a alguém, "ei, por favor, vigie a minha formiga e registre o trajeto que ela fez a cada parada". Essa área é tão importante, que merece um capítulo, o próximo, porque eu não clebista.

## A área de stage

O git divide basicamente um diretório, em três seções:

1. Diretório
2. Stage
3. Repositório

Vamos falar sobre cada um deles:

### Diretório

Neste, ficam os arquivos que ainda não foram rastreados, ou os arquivos que já foram rastreados e ainda não tiveram as mudanças nele, declaradas ao git, portanto, ainda não foram enviados para o stage (de início é complexo, mas com o exemplo, você vai entender, a pílula vermelha desce com dificuldade, mas desce).

### Stage

Esta é a área em que fica o arquivo após ter sido rastreado, ou ter tido as mudanças feitas em si, rastreadas. A partir daqui, ele já pode ser enviado para o repositório do git, que é onde fica armazenados os commits, que são como a versão final das modificações, já na forma como de fato deveriam ser.

Então, agora vamos ao exemplo.

Criamos o arquivo _lista.txt_, se verificarmos o status do git por meio de ```git status``` teremos o seguinte resultado:

```
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	lista.txt

nothing added to commit but untracked files present (use "git add" to track)
```

Veja que ele está localizado na seção _untracked files_, isso significa que está meramente no diretório, mas que não cabe ao git responsabilidade alguma sobre ele, já que, não foi declarado como um item a ser rastreado, portanto, vamos rastreá-lo e isso irá dispô-lo na área de stage:

```bash
$ git add lista.txt
$ git status
```
Agora temos como resposta:

```
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   lista.txt

```

Agora ele se encontra na seção _Changes to be commited_ e isso significa que ele está na área de stage, pronto para ser devidamente gravado como uma versão final de si mesmo, o que irá colocá-lo na área de commit, o chamado repositório ou ambiente de arquivos gravados. Se nós o alterarmos, ele volta para o diretório, pois apesar de estar rastreado, as mudanças feitas ainda não foram declaradas por meio do ```git add lista.txt```, mas, já que podemos gravá-lo (fazer um commit), então o faremos por meio do comando ```git commit``` que possui a seguinte sintaxe:

```
$ git commit -m "Meu primeiro commit"

A opção -m é como uma mensagem que rotula o commit e ela é obrigatória, se você não colocá-la, um editor de texto será aberto para que algo seja escrito. E isso nos dará a seguinte resposta:

```
[master (root-commit) 825cfd1] Meu primeiro commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 lista.txt
```