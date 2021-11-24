# Layouts e evolução 

Layout tem a ver com a maneira que os elementos estão distribuidos na tela

## Normal flow

Ou Flow Layout é a maneira que os elementos `block` e `inline` ficam na página

```html
    <p> Texto block com <strong>inline</strong> dentro </p>
```

# Tables

É a maneira de tabelas da qual a tag `table`recebe um display `table` fazendo com que os elementos internos como `td`e `tr` possam ser usados para montar uma tabela

```html
    <table>
        <tr>
            <td> Hora </td>
            <td> 17:00 </td>
        </tr>
        <tr>
            <td> Hora </td>
            <td> 17:30 </td>
        </tr>
    </table>
```

# Tabless

Uso das propriedades `float`,`clear` para que os elementos possma mudar de posição na tela.

```html
    <div style = "float: left;">
        esquerda
    </div>

    <div style = "float: right;">
        direita
    </div>

    <div style = "clear: both;">
        normal
    </div>
```

## Flexbox

A caixa se torna flex, fazendo com que os elementos internos possam receber melhor:

- Alinhamento
- Ordenação
- Tamanhos flexíveis

```css
    .flexbox{
        display: flex;
        justify-content: space-around;
    }
```

```html
    <div class="flexbox">
        <div class="item">A</div>
        <div class="item">B</div>
        <div class="item">C</div>
    </div>

```

# Terminologia
- Flex Container
  - -Flex item
- Nesting (elementos vivem dentro de outros elementos)
- Axis (eixo)
  - main(x)
    - star,end
  - cross(y)
    - star, end
- Flex sizing
  - flexível
  - altera width/height dos itens para preenchimento dos espaços do flex container


# Propriedades do Flex Container

* Direção dos itens 
* Multi linhas
* Alinhamento
  * Principal
  * Cruzado
* Espaços entre os itens

## Direção dos internos

- Flex é uma dimensão (horizontal e vertical)
- Podemos mudar a direção com `flex-direction`
- valores(row(normal) | row-reverse(espelhado) | column(em pé) | column-reverse(em pé e espelhado[para ver melhor, adicone um `height` ao container]))
- Eixo cruzado é o contrário do eixo que está sendo citado. Caso seja o eixo cruzado de uma row, o eixo é na vertical e se for de uma column na horizontal. 

## Flex-wrap(multi linhas)

- Podemos usar multi linhas.
- Cada nova linha, um novo flex container

```html
    <div class="box">
            <div>A</div>
            <div>B</div>
            <div>C</div>
            <div>D</div>
        </div>
```

```css
.box{
    display: flex;
    flex-wrap: wrap;
    border: 1px dashed red;
}

.box div {
    border: 1px solid;
    width: 80px;
}
```

## Flex-flow

- Shorthand
- flex-direction || flex-wrap

```html
    <div class="box">
            <div>A</div>
            <div>B</div>
            <div>C</div>
            <div>D</div>
        </div>
```

```css
.box{
    display: flex;
    flex-flow: row wrap; /*pode usar duas propriedades se quiser*/
    border: 1px dashed red;
}

.box div {
    border: 1px solid;
    width: 80px;
}
```

## Justify-content

- Alinhamento dos elementos dentro do container
- Distribuição dos elementos 

### Valores

- Flex-start
- Flex-end
- Center
- Space-around
- Space-between
- Space-evenly


```html
    <div class="box">
            <div>A</div>
            <div>B</div>
            <div>C</div>
            <div>D</div>
        </div>
```

```css
.box{
    display: flex;
    justify-content: flex-start;/*colado na esquerda*/
    justify-content: flex-end;/*colado na direita*/
    justify-content: center;/*centralizado*/
    justify-content: space-around;/*espaços por igual ao redor deles, menos no início e no final */
    justify-content: space-between;/*espaços por igual ao redor deles, porém com o primeiro colado na esquerda e o último colado na direita*/
    justify-content: space-evenly;/*espaços por igual ao redor deles desde o início até o final */
    border: 1px dashed red;
}

.box div {
    border: 1px solid;
    width: 80px;
}
```

## Align-items

- Alinhamento dos elementos no eixo cruzado(y)

### Valores 

- Stretch
- Flex-start
- Flex-end
- Center
  
```html
    <div class="box">
            <div>A</div>
            <div>B</div>
            <div>C</div>
            <div>D</div>
        </div>
```

```css
.box{
    display: flex;
    align-items: stretch;/*Já é por padrão, porém, deixa os elementos esticados*/
    align-items: flex-start;/*Deixa os elementos no começo do eixo cruzado*/
    align-items: flex-end;/*Deixa os elementos no final do eixo cruzado*/
    align-items: center;/*Deixa os elementos no centro do eixo cruzado*/
    border: 1px dashed red;
}

.box div {
    border: 1px solid;
    width: 80px;
}
```

## Gap 

- Espaços entre os elementos

### Valores 

- Unidades de medidas:
  -  fixas: pc, pt;
  -  flexíveis: %, em, rem;


```html
    <div class="box">
            <div>A</div>
            <div>B</div>
            <div>C</div>
            <div>D</div>
        </div>
```

```css
.box{
    display: flex;
    border: 1px dashed red;
    gap: 2%;/* em, rem*/
}

.box div {
    border: 1px solid;
    width: 80px;
}
```

# Propiedades para os itens

- flex-basis(tamanho do item)
- flex-grow(faz o item crescer automaticamente)
- flex-shrink(comprimir o item)
- flex(shorthand dos 3 acima)
- order(ordenar elementos)

## flex-basis

```html
    <div class="box">
            <div>A</div>
            <div>B</div>
            <div>C</div>
            <div>D</div>
        </div>
```
```css
.box{
    display: flex;
    border: 1px dashed red;
}

.box div {
    border: 1px solid;
    flex-basis: auto;/*por padrao ja eh auto*/
}
```

- Não é possível realizar a alteração em `.box div:nth-child(1)`, pois em `.box div` foi feita uma alteração primeiro.

```html
    <div class="box">
            <div>A</div>
            <div>B</div>
            <div>C</div>
            <div>D</div>
        </div>
```
```css
.box{
    display: flex;
    border: 1px dashed red;
}

.box div {
    border: 1px solid;
    flex-basis: 25%;
}

.box div:nth-child(1){
    width: 25px;
}
```

- É possível realizar a modificação a baixo, pois em `.box div`, flex-basis está como auto, permitindo  com quem seja trabalhada a altura em seu eixo principal.box

```html
    <div class="box">
            <div>A</div>
            <div>B</div>
            <div>C</div>
            <div>D</div>
        </div>
```
```css
.box{
    display: flex;
    border: 1px dashed red;
}

.box div {
    border: 1px solid;
    flex-basis: auto;
}

.box div:nth-child(1){
    width: 25px;
}
```

## flex-grow

- O crescimento do item dentro do container em relaçao aos espaços vazios.

```html
    <div class="box">
            <div>A</div>
            <div>B</div>
            <div>C</div>
            <div>D</div>
        </div>
```
```css
.box{
    display: flex;
    border: 1px dashed red;
}

.box div {
    border: 1px solid;
}

.box div:nth-child(3){
    flex-grow: 1;/*No elemento referenciado, adiciona a parcela que deseja do espaço em branco que sobrou do box*/
}
```

## flex-shrink

- O encolher do item dentro do container

```html
    <div class="box">
            <div>A</div>
            <div>B</div>
            <div>C</div>
            <div>D</div>
        </div>
```
```css
.box{
    display: flex;
    border: 1px dashed red;
}

.box div {
    border: 1px solid;
    flex-basis: 80px;
}

.box div:nth-child(3){
    flex-shrink: 2;
}
```

## flex

- shorthand
- flex-grow flex-shrink flex-basis
- podem ter 1, 2 ou 3 valores


## Alterando tamanho de múltiplos itens

```css
    .page{
        border: 2px solid;
        min-height: 100vh;
        display: flex;
    }

    aside{
        background: lightgreen;
        flex: 1;/*flex-grow | flex-shrink | flex-basis*/
    }

    main{
        background: lightblue;
        flex: 2;

        display: flex;
        flex-direction: column;
    }

    main section:nth-child(1){
        background: lightpink;
        flex: 1;
    }

    main section:nth-child(2){
        background: lightcoral;
        flex: 0 250px;
    }

    main section:nth-child(3){
        background: lightsalmon;
        flex: 1;
    }
```
```html
    <div class="page">
        <aside>Aside</aside>
        <main>
            Main
            <section>Content 1</section>
            <section>Content 2</section>
            <section>Content 3</section>
        </main>
    </div>
```

## order

- Ordernar elementos dentro de uma caixa 
- Serve como maneira visual, não estrutural, ou seja, não altera o HTML

```css
.box{
    display: flex;
    border: 1px dashed red;
}

.box div:nth-child(1){
    border: 1px solid;
}

.box div:nth-child(2){
    border: 1px solid;
}

.box div:nth-child(3){
    border: 1px solid;
}

.box div:nth-child(4){
    border: 1px solid;
}


.box div:nth-child(1){
    order: 1;
}

.box div:nth-child(2){
    order: 0;
}

.box div:nth-child(3){
    order: 2;
}

.box div:nth-child(4){
    order: -1;
}
```

```html
    <div class="box">
        <div>A</div>
        <div>B</div>
        <div>C</div>
        <div>D</div>
    </div>
```