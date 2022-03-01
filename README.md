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
