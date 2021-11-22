# Seletores
 
Conecta um elemento HTML com o CSS a fim de alterar o elemento

## Tipos

* Element Selector
    - Todos os elementos HTML para

* ID Selector (#nomedoid)
    - Um elemento que tenha um atributo 'id'.

* Class Selector (.nomedaclass)
    - Os elementos que contenham um atributo 'class'.
    - Podemos ter uma ou mais classes.

* Atribute Selector ([nomedoseletor] // no html fica por exemplo ' title= "pagina 1 e assim vai, sem ter que ter o conteudo dentro do atributo igual em todos, so o nome do atributo" '
    - Um elemento que tenha um atributo específico

* Pseudo-class Selector
    - Elementos em um estado específico.



# Combinators

Combbinadores, pois eles trabalham para buscar e combinar seletores a gim de aplicar uma estilização

## Descendant combinator

* Identificado por um espaço entre os seletores.
* Busca um elemento dentro de outro

```css
body article h2{
    color: red;
} 
```

``` HTML
<body>
    <article>
        <h2>
            titulo 1 (aqui vai ser vermelho se no CSS estiver escrito da maneira ali de cima)
        </h2>
    </article>
</body>
```

# Child combinator

* Identificado pelo sinal ` > ` entre dois elementos
* Seleciona somente o elemento que é filho direto do pagina
* Elementos depois do filho direto serão desconsiderados

```css
body > ul > li{
    color: red;
} 
```
``` HTML
<body>
    <ul>
        <li>Item 1</li>
    </ul>

    <ul>
        <li>Item 2</li>
    </ul>

    <div> //esse não colore, pois não está na direção correta que é citada no css
        <ul>
        <li>Item 3</li>
    </ul>  
    <ul>
        <li>Item 4</li>
    </ul>
    </div>

</body>
```

# Adjacent sibling combinator

* Identificado pelo sinal ` + ` entre dois seletores 
* Seleciona somente o elemento do lado direito que é irmão direto na hierarquia

```css
h1 + p{
    color: red;
} 
```

``` HTML
    <h1>
        titulo
    </h1>

    <p>
        paragrafo 1 //vai colorir esse pq eh o irmão direto do h1
    </p>

    <p>
        paragrafo 2
    </p>
```


```css
h1 ~ p{
    color: red; //vai colorir todos os irmaos de h1, ou seja, todos os 'p's que vem dps dele
```

``` HTML
    <h1>
        titulo
    </h1>

    <p>
        paragrafo 1 
    </p>

    <p>
        paragrafo 2
    </p>
```


