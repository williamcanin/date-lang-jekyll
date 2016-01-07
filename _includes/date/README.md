# Date Lang Jekyll - The date on the language.

"Data Lang Jekyll" is a plugin for templates in Jekyll in order to include the date (% m% d,% Y - with name of month extensive ) in Posts and Pages.

## Usage

* Step 1: Enter **_includes** folder of your template Jekyll and download the *Date Lang Jekyll*

```
cd /go/to/path/_includes
git clone https://github.com/williamcanin/date-lang-jekyll.git "date"
```

* Step 2 : Enter **date** folder

```
cd ./date
```

* Step 3: Setting the Date Lang Jekyll

Após realizar o clone do *Date Lang Jekyll*, terá que configura-lo com o script **"setup.sh"**.

**Gerando conteúdo dos idiomas**

A primeira configuração é gerar o conteúdo dos arquivos de idiomas, pois estão codificados com hexadecimal. Para isso, faça:

```
$ ./setup.sh --init
```

**Escolhendo seu idioma**

Após gerar o conteúdo dos idiomas, o *Date Lang Jekyll* vai fazer uma pergunta se você deseja escolher o seu idioma e manter somente ele. 
Você pode cancelar, porem irá manter todos os idiomas do *Date Lang Jekyll*. 

Você deve escolher pela numeração. Veja abaixo um exemplo de como irá retornar no seu console:

| Column 1 | Column 2 | Column 3 | Column 4 | Column 5 |
|----------|----------|----------|----------|----------|
|1) ch_CH  | 3) en_US | 5) fr_FR | 7) ja_JP | 9) ru_RU |
|2) de_DE  | 4) es_ES | 6) it_IT | 8) pt_PT |10) Cancel|

**Configurando variáveis para posts and pages**

Por padrão, as variavés de posts e pages do *Date Lang Jekyll* é: **post** e **page**, mas, o *Date Lang Jekyll* tem o recurso de alteração do nome dessas variáveis de posts e pages. 

*Perguntas:*

> Como assim?

R: Quando se cria uma lista de posts no Jekyll por exemplo, o mesmo necessita de uma variável que esteje presente em um laço (for) no Jekyll para armazenar essa lista.

Exemplo:

```
{% for posting in site.posts %}
   {{ posting.title }}
{% endfor %}  
```

Repare que o laço (for) irá me retornar uma listagem de posts e armazenar na variável **posting** e mostrar o título do post.

> Mas se a minha variável é **posting** e a padrão do *Date Lang Jekyll* é 
> **post**, como eu altero?

R: Agora vem a ultima configuração. Para fazer essa alteração de variáveis para posts e pages. Use os comando abaixo:

**Alterando variável para posts**

```
$ bash ./setup.sh --post posting 
```

**Alterando variável para pages**

```
$ bash ./setup.sh --page pages
```


* Step 4: Including plugin *Date Lang Jekyll*

Vamos testar?!

No seu template Jekyll, incorpore o plugin *Date Lang Jekyll* com a seguinte linha:

```
{% include date/lang/en_US.jk %}
```


## License

[MIT License (MIT)](https://opensource.org/licenses/MIT)
