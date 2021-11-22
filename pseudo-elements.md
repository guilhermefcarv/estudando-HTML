# Pseudo-elements

Com pseudo-elements nós podemos adicionar elementos HTML pelo próprio CSS

` ::pseudo-element-name`

## Exemplos

* ::before

```Css
li::before{ 
  content: "> "  
}
```

```HTML
<li>A1</li>
<li>B2</li>
<li>C3</li>
<li>D4</li>
```


* ::after

```Css
li::after{ 
  content: "> "  
}
```

```HTML
<li>A1</li>
<li>B2</li>
<li>C3</li>
<li>D4</li>
```

* ::first-line

```Css
p:nth-of-type(2)::first-line {
  font-weight: bold;
}
```

```HTML
<p>
  Lorem ipsum dolor sit amet consectetur adipisicing elit. Perferendis deleniti quae cum quas distinctio fugiat tempore, ratione iusto consequuntur voluptates rerum delectus omnis beatae velit officiis facilis totam eligendi possimus quibusdam. Aliquid dolorum veniam praesentium molestias qui tenetur odit optio id aperiam, exercitationem et odio commodi cum, voluptatum quam eum.
</p>

<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam enim voluptas sint laudantium tempore sed quisquam accusantium sapiente aliquam necessitatibus itaque non suscipit laborum delectus ea facere dolorem, error earum.</p>

<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Laborum veniam praesentium laudantium, illo exercitationem quod suscipit, modi voluptatibus libero maxime, recusandae earum eaque inventore quidem magnam nemo consectetur officiis accusantium?</p>
```

## Referência

https://developer.mozilla.org/en-US/docs/CSS/Pseudo-elements