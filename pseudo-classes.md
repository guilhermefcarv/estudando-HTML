# Pseudo-classes

É um tipo de seletor que irá selecionar um elemento que estiver em um estado específico.

Exemplo: É o primeiro elemento dentro de uma caixa, ou, o elemento está com o ponteiro do mouse em cima dele.

Pseudo-classes começam com 2 pontos seguido do  nome pseudo class

## Selecionando elementos com pseudo-classes

* :first-child
* :nth-of-type()
* :nth-child()


```css
ul li:first-child {
  font-weight: bold;
}
```

```HTML
<ul>
    <li>A</li>
    <li>B</li>
    <li>C</li>
</ul>
```



```css
ul li:nth-of-type(2) { 
  font-weight: bold;
}
```

```HTML
<ul>
    <h3>Letras</h3>
    <li>A</li>
    <li>B</li> //colore esse, pq pega como referencia apenas os 'li' e retira o h3 da familia
    <li>C</li>
</ul>
```



```css
ul li:nth-child(2) { //pega como referencia os filhos, sem excluir o h3, uma vez que ele faz parte da filhagem e depende 
  font-weight: bold;
}
```

```HTML
<ul>
    <h3>Letras</h3>
    <li>A</li>
    <li>B</li> //colore esse, pq pega como referencia apenas os li e retira o h3 da familia
    <li>C</li>
</ul>
```



```css
ul li:nth-child(even) { //altera apenas os impares (odd para os pares)
  font-weight: bold;
  color: red;
}
```

```HTML
<ul>
    <h3>Letras</h3>
    <li>A</li>
    <li>B</li> //colore esse, pq pega como referencia apenas os li e retira o h3 da familia
    <li>C</li>
</ul>
```



## Ações do usuário

* :hover
* :focus

```css
a:hover {
  color: red;
}

input:focus {
  border-color: red;
  outline: none;
}
```

``` HTML
<a href="#">Clique aqui</a>

<input type="text">
```


## Atributos 

* :disable
* :required


```css
input:disabled {
  border-color: red;
}

input:required {
  border-color: green;
}
```

``` HTML
<input type="text" disabled>

<input type="text">

<input type="text" required>

<input type="text">
```


## Referência

https://developer.mozilla.org/en-US/docs/CSS/Pseudo-classes

