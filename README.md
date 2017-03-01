# Guia de Estilo HTML

<img
  src="https://raw.github.com/caiogondim/html-style-guide/master/logo.png"
  alt="HTML style guide logo"
  align="right"
/>

> Um guia de estilo é sobre consistência. Consistência neste guia de estilo é
> importante. Consistência em um projeto é mais importante. Consistência em
> um módulo ou função é ainda mais importante.
>
> Mas mais importante: saiba quando ser inconsistente -- às vezes esse guia de estilo
> simplesmente não é aplicável. Quando estiver em dúvida, use seu melhor argumento. Veja por
> exemplos de outros e decida o que parece melhor. E não hesite em perguntar:
>
> PEP 8, Python


## Protocolo

Omita o protocolo (http:, https:) das URLs apontando para imagens, folhas de estilo
scripts, exceto se eles não tiverem disponíveis nos dois protocolos. Dessa forma, conteúdo
mixo será prevenido, uma vez que a URL agora é relativa.

```html
<!-- Bom -->
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js"></script>

<!-- Ruim -->
<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js"></script>

```
```css
/* Bom */
.example {
   background: url(//caiogondim.com/img/logo.png);
}

/* Ruim */
.example {
   background: url(http://caiogondim.com/img/logo.png);
}
```

## Indentação

Sempre use 2 espaços para indentação.

```html
<html>
  <head></head>
  <body>
    <section></section>
  </body>
</html>
```


## Capitalização

Use apenas letras minúsculas.

```html
<!-- Ruim -->
<A HREF="/">Home</A>

<!-- Bom -->
<a href="/">Home</a>
```


## Tipo de Documento

Use HTML5. E use síntaxe HTML, não XHTML. Hixie
[escreveu um pouco sobre isso](http://hixie.ch/advocacy/xhtml) (O link é em inglês e não foi traduzido).

```html
<!--- Ruim -->
<br />

<!-- Bom -->
<br>

<!-- Bom -->
<!doctype html>

<!-- Ruim -->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
```


## Separação de Referências

Em seus templates e documentos, use apenas (ou se esforce para usar) HTML. Coloque
tudo que for everything de apresentação em folhas de estilo. E todos os comportamentos em
arquivos de script.

Deixe a área de contato o mais simples possível, linkando apenas as folhas de estilos necessárias e
os scripts para o documento atual.


```html
<!-- Ruim -->
<!doctype html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Example</title>
</head>
  <body>
    <h1 style="font-size: 20px;">Lorem Ipsum</h1>
  </body>
  <script>
    document.querySelector("h1").style.color = "red";
  </script>
</html>

<!-- Bom -->
<!doctype html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Example</title>
  <link rel="stylesheet" href="main.css">
</head>
  <body>
    <h1>Lorem Ipsum</h1>
  </body>
  <script src="app.js"></script>
</html>
```


## Referências de entidades

Não há necessidade de utilizar referências de entidades como `&rdquo;` ou `&mdash;` se vocÊ estiver
utilizando a formatação UTF-8. As únicas exceções são os caracteres com significados especiais para o
HTML, como `<`, `>` e `&`, ou caracteres "invisíveis" como espaços sem interrupção.

```html
<!-- Ruim -->
O símbolo da Moeda do Euro é &ldquo;&eur;&rdquo;.

<!-- Bom -->
O símbolo da Moeda do Euro é “€”.

<!-- Ok, pois queremos sempre que "Mr." e "Alguém" fiquem juntos e nunca em linhas separadas -->
Mr.&nbsp;Someone
```


## Tags de fechamento automático

Use a forma do HTML5 e não do XHTML.

```html
<!-- Ruim -->
<br />
<hr />

<!-- Bom -->
<br>
<hr>
```


## Atributos

Novamente, prefira a forma do HTML5 e não do XHTML.

```html
<!-- Ruim -->
<input type="checkbox" checked="checked">

<!-- Bom -->
<input type="checkbox" checked>
```


## Aspas

Use sempre duas aspas.

```html
<!-- Ruim -->
<input type=checkbox>
<input type='checkbox'>

<!-- Bom -->
<input type="checkbox">
```


## Máximo comprimento de linhas

Tente o máximo que você puder em manter o comprimento da linha menor que 80 colunas.
Melhora a legibilidade e torna possível usar visualização de duas colunas em seu editor
(seu editor suporta isso, certo?) sem precisar de scroll horizontal.

```html
<!-- Ruim -->
<img class="block__element" id="unicorn" src="http://cl.ly/image/1a1U013E002Z" alt="Unicorn, rainbows, poop and stuff" width="500">

<!-- Bom -->
<img
  class="block__element"
  id="unicorn"
  src="http://cl.ly/image/1a1U013E002Z"
  alt="Unicorn, rainbows, poop and stuff"
  width="500"
>
```

Além disso, é uma boa prática manter todos os atributos em linhas separadas, pois o Git não exibe num diff
em qual linha **algo** foi modificado, apenas o que foi modificado em si.


## Referências

Este documento é altamente inspirado em outros guias de estilo:
- [Google HTML/CSS Guide](https://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml)
