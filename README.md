# CssGridLayout

## Grid Container
O Grid Container é a tag que envolve os itens do grid, ao indicar `display: grid;` , essa tag passa a ser um Grid Container.

### 1 • display
Define o elemento como um grid container.
<br/>
<br/>

`display: grid;`<br/>
> Torna o elemento um grid container.
<br/>
<br/>

`display: inline-grid;`<br/>
> Torna o elemento um grid container porém com comportamento inline.
<br/>
<br/>

`display: subgrid;`<br/>
> Para grids dentro de grids (ainda não é suportado, porém você pode normalmente colocar `display: grid;` no grid dentro do grid que funciona).
<br/>
<br/>

### 2 • grid-template-columns
Define o número total de colunas que serão criadas no grid.
<br/>
<br/>

`grid-template-columns: 100px 100px 100px 100px;`<br/>
> Quatro colunas de 100px de largura são criadas
<br/>
<br/>

`grid-template-columns: 1fr 2fr;`<br/>
> Duas colunas são criadas, sendo a segunda com o dobro do tamanho da primeira. **fr** é uma unidade fracional. O tamanho do conteúdo é respeitado, ou seja, se o conteúdo na primeira coluna for maior que o da segunda, a primeira será maior.
<br/>
<br/>

`grid-template-columns: minmax(200px, 1fr) 1fr 1fr;`<br/>
> Três colunas são criadas, a primeira terá no mínimo **200px** de largura e no máximo **1fr** (isso significa que após **200px** ela se expande da mesma forma que as outras colunas). As outras duas colunas vão ter **1fr**.
<br/>
<br/>

`grid-template-columns: repeat(3, 1fr);`<br/>
> Cria 3 colunas com **1fr** de tamanho. O repeat seria a mesma coisa que escrever **1fr 1fr 1fr**.
<br/>
<br/>

`grid-template-columns: repeat(auto-fit, minmax(100px, auto));`<br/>
> Cria automaticamente um total de colunas que acomode itens com no mínimo **100px** de largura.
<br/>
<br/>

### 3 • grid-template-rows
Define a quantidade de linhas no grid.
<br/>
<br/>

`grid-template-rows: 50px 100px 50px 150px;`<br/>
> Cria 4 linhas no grid, sendo a primeira com 50px, segunda 100px, terceira 50px e quarta 150px. Caso o grid necessite de mais linhas, elas terão o tamanho de acordo com o conteúdo.
<br/>
<br/>

`grid-template-rows: 1fr 2fr;`<br/>
> Cria 2 linhas no grid, sendo a segunda com cerca de duas vezes o tamanho da primeira.
<br/>
<br/>

### 4 • grid-template-areas
Define áreas específicas no grid. O ponto (.) pode ser utilizado para criar áreas vazias.
<br/>
<br/>

```
grid-template-areas:
"logo nav nav"
"sidenav content advert"
"sidenav footer footer";
```
> Cria 3 colunas e 3 linhas. [logo] ocupa a coluna 1, linha 1. [nav] ocupa da coluna 2 a 3, linha 1. [sidenav] ocupa a coluna 1, da linha 2 a 3. [content] ocupa a coluna 2, linha 2. [advert] ocupa a coluna 3, linha 2. [footer] ocupa da coluna 2 a 3, linha 3.
<br/>
<br/>

### 5 • grid-template
Atalho para definir o `grid-template-columns`, `grid-template-rows` e `grid-template-areas`.
<br/>
<br/>
```
grid-template:
"logo nav nav" 50px
"sidenav content advert" 150px
"sidenav footer footer" 100px
/ 100px 1fr 50px;
```

> A primeira linha com 50px, segunda com 150px e terceira com 100px. A primeira coluna com 100px, a segunda 1fr e a terceira com 50px.
<br/>
<br/>

### 6 • gap
Define o gap (gutter) entre os elementos do grid.
<br/>
<br/>

`gap: 20px;`<br/>
> Define 20px entre os elementos do grid (linha e coluna).
<br/>
<br/>

`column-gap: 20px;`<br/>
> Define 20px de distância entre as colunas.
<br/>
<br/>

`row-gap: 20px;`<br/>
> Define 20px de distância entre as linhas.
<br/>
<br/>

### 7 • grid-auto-columns
Define o tamanho das colunas do grid implícito (gerado automaticamente, quando algum elemento é posicionado em uma coluna que não foi definida).
<br/>
<br/>

`grid-auto-columns: 100px;`
> As colunas implícitas, geradas automaticamente, terão 100px de largura.
<br/>
<br/>

### 8 • grid-auto-rows
Define o tamanho das linhas do grid implícito (gerado automaticamente, quando algum elemento é posicionado em uma linha que não foi definida).
<br/>
<br/>

`grid-auto-rows: 100px;`
> As linhas implícitas, geradas automaticamente, terão 100px de altura.
<br/>
<br/>

### 9 • grid-auto-flow
Define o fluxo dos itens no grid. Se eles vão automaticamente gerar novas linhas ou colunas.
<br/>
<br/>

`grid-auto-flow: row;`
> Automaticamente gera novas linhas.
<br/>
<br/>

`grid-auto-flow: column;`
> Automaticamente gera novas colunas.
<br/>
<br/>

`grid-auto-flow: dense;`
> Tenta posicionar o máximo dos elementos que existirem nas primeiras partes do grid (pode desorganizar o conteúdo).
<br/>
<br/>

### 10 • grid
Atalho geral para definir o grid: `grid-template-rows`, `grid-template-columns`, `grid-template-areas`, `grid-auto-rows`, `grid-auto-columns` e `grid-auto-flow`.
<br/>
<br/>

`grid: 100px / 1fr 1fr;`
> Gera uma linha com 100px de altura e 2 colunas com 1fr.
<br/>
<br/>

`grid: 100px / auto-flow 100px 50px;`
> Gera uma linha com **100px** de altura. O `grid-auto-flow` é definido como **column** (pois está logo antes da definição das colunas). Ele também define o `grid-auto-columns` com **100px** **50px**.
<br/>
<br/>

### 11 • justify-content
Justifica os itens do grid em relação ao eixo x (horizontal).
<br/>
<br/>

`justify-content: start;`
> Justifica os itens ao início.
<br/>
<br/>

`justify-content: end;`
> Justifica os itens ao final.
<br/>
<br/>

`justify-content: stretch;`
> Estica os itens.
<br/>
<br/>

`justify-content: space-around;`
> Distribui espaço entre os elementos. (O início e final são menores que os espaços internos).
<br/>
<br/>

`justify-content: space-between;`
> Cria um espaço entre os elementos, ignorando o início e final.
<br/>
<br/>

`justify-content: space-evenly;`
> Cria um espaço igual entre as colunas (no início e final também).
<br/>
<br/>

`justify-content: center;`
> Centraliza o conteúdo.
<br/>
<br/>

### 12 • align-content
Alinha os itens do grid em relação ao eixo y (vertical).
<br/>
<br/>

`align-content: start;`
> Alinha os itens ao início.
<br/>
<br/>

`align-content: end;`
> Alinha os itens ao final.
<br/>
<br/>

`align-content: stretch;`
> Estica os itens.
<br/>
<br/>

`align-content: space-around;`
> Distribui espaço entre os elementos. (O início e final são menores que os espaços internos).
<br/>
<br/>

`align-content: space-between;`
> Cria um espaço entre os elementos, ignorando o início e final.
<br/>
<br/>

`align-content: space-evenly;`
> Cria um espaço igual entre as colunas (no início e final também).
<br/>
<br/>

`align-content: center;`
> Centraliza o conteúdo.
<br/>
<br/>






















