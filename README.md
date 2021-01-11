# Versionando com Git e GitHub

## Você já deve saber, mas vamos repetir.

Git é um versionador de código, um sistema, e para utilizá-lo em seus projetos, não há necessidade alguma de você usar a internet para fazer as operações.

Já o GitHub, ele é um repositório. Ou seja, trata-se de uma hospedagem para códigos versionados pelo sistema GIT. Então, o seu código local, versionado com git, com commits e branchs de várias ordens, pode ser enviado para o GitHub e assim você pode dar acesso público ou não ao seu código. Mas, de toda forma, ele permanece seguro nos registos do site. Você viaja e esquece de levar consigo uma cópia do seu código, mas não há problema, pois se você tiver feito a hospedagem dele no GitHub, tudo o que precisará para acessá-lo será o seu login e senha.

## Começando com o GIT

Partindo do pressuposto que você já instalou o git no seu computador, vamos começar pelas configurações primordiais: os dados de quem irá operar o versionador na sua máquina, é você mesmo, não é?

```bash
$ git config --global user.name "Daniel Castro"
$ git config --global user.email "daniel@email.com"
```

Pronto, uma vez que você inseriu seus dados nas configurações, agora você pode listá-las por meio de:

```bash
$ git config --global --list
```
