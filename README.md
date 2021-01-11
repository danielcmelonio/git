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

Se fizermos o ```bash git status ``` outra vez, agora veremos o nome do nosso arquivo em verde, isso significa que ele agora está de fato sendo rastreado pelo git, e que as alterações nele, estão sendo devidamente monitoradas, algo que vai nos ser muito útil a qualquer tempo do ciclo de vida do projeto.
