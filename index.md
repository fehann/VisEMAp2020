# Visualização da Informação - Fernando Hannaka

Este trabalho faz parte do curso de Visualização da Informação do EMAp da FGV.

## Aula 2 - Criar a visualização do Quarteto de Ascombe

A ferramenta escolhida para criar as visualizações foi o Altair em Python. Eu tenho mais fluência na utilização do R, usei uma vez o Altair porém foi baseado em um código template, portanto escolhi esta ferramenta para testar fazer visualizações do zero e aumentar minhas habilidades em programação.

### Dados

Os dados foram obtidos do [site da Wikipedia](https://pt.wikipedia.org/wiki/Quarteto_de_Anscombe) e transformados no [formato em csv](https://github.com/fehann/VisEMAp2020/blob/master/Anscombe.csv).

### Visualização padrão

O primeiro passo foi recriar a visualização padrão do quarteto. Uma dificuldade maior nesta parte foi encontrar a maneira de plotar a linha de regressão pois em um primeiro momento não funcionou. Após várias buscas encontrei a solução que é a utilização de layers para plotar um gráfico sobre o outro.

<img 
    src="Viz1.svg" 
    alt="Quarteto de Anscombe"
 />

### Visualização interativa

Esta visualização interativa permite selecionar cada categoria separadamente e visualizar como os pontos diferem em relação aos outros conjuntos de dados. Foi adicionado também gráficos auxiliares nos eixos x e y mostrando o posicionamento dos pontos em cada eixo por categoria. É interessante que pela visualização fica claro que em quase todas as categorias, exceto a IV, todos os pontos estão na mesma coordenada x, o que difere é o posicionamento no eixo y onde as suas variações resultam na linha de regressão linear ser as mesmas para todas.

<img 
    src="Viz2.svg" 
    alt="Quarteto de Anscombe"
 />

Segue abaixo o código para esta visualização interativa, 

```markdown

# Configure the options common to all layers
brush = alt.selection_single(fields=['Category'])
base = alt.Chart(df).add_selection(brush)

# Configure the points
points = base.mark_circle(size=60).encode(
    x=alt.X('x', title=''),
    y=alt.Y('y', title=''),
    color=alt.condition(brush, 'Category', alt.value('lightgrey'))
)

# Configure the ticks
tick_axis = alt.Axis(labels=False, domain=False, ticks=False)

x_ticks = base.mark_tick().encode(
    alt.X('x', axis=tick_axis),
    alt.Y('Category', title='', axis=tick_axis),
    color=alt.condition(brush, 'Category', alt.value('lightgrey'))
)

y_ticks = base.mark_tick().encode(
    alt.X('Category', title='', axis=tick_axis),
    alt.Y('y', axis=tick_axis),
    color=alt.condition(brush, 'Category', alt.value('lightgrey'))
)

# Build the chart
finalcombo = y_ticks | (points & x_ticks)

finalcombo.properties(
    title='Quarteto de Anscombe'
).configure_title(
    fontSize=23,
    anchor='middle'
)

```

[Open the Chart in the Vega Editor](https://vega.github.io/editor/#/url/vega-lite/N4Igxg9gdgZglgcxALlANzgUwO4tJKAFzigFcJSBnAdTgBNCALFAFgAY2AacaYsiygAlMiRoRQBmDgF9p3OgENCCvCCgKAtphQhFygLQAOQwCZDEgEZ0TARgCsdiZkMw7Nm+YCcmMGBsKAdkMLBxMQORANBQAnAGtVQgBPAAdtZHA4aLAAG21uSjgALzSANjYIzChIOhIkVB5siGiElLS1CA0SBWyQbnhMbLodAGElTAQmxPDuQggIbOJklABtUCTUnSgOrp6+rEGRsYnoqbk11p0AR1IFIjhlYjQ8kH6D9IAPafON9Ovb4gecCevRe+yG6VOAF1uJ96us2n87oDgXsBuCQJ8IlM4RdfjckUogc9XujThFKAMfMRoKoKbkwLNomw7CUWj8QAUoAhciCSZQViBRoRxpMQJDZNwACSUMCMTBRHRiQjJSjIAD0aqeCAUADoEPdGKQLDq4BA1TK5VFNeMFPpsvdMJqWDrDDqbDqAFaUGnyJQKCmEfn1PS24xmSzWeyOZyudxeHx+QLBUIrUBCkUnHQASRBsJsXBA2NdbBYZ0FR1F6RzMJQhm42JKOs8djL6eO2JA1YxKBsEnrKACOrshlbFczVdzKE8-eQrsMNlHwvb2cnyHcM9dEgki4zHa7eZYM88TZKO+XE5ryBKM8HJlLnDTY73q8PhdYOpMp4f5aXlc7q5sEwZ3zF170fX9x3-S8AhnZ1TDPP99xQOwZzsHUShHb820QpC1wLbFjxsMCf13bNcLrN9ZzdYjsMgrNcN7DcdQCGinzI1dp0o10AgCBC6IYmwjw-L9wNIqsGNfIs3T4vdcOvSjG17GT2MvSTJGkrC2PEgCgMowjt00iDZNXGDKNvESSPPTtcJQyjnRY5TxIY-CBx1FgLNo2TyJnRseMc6yGL7SjAOY1ijLI3DOOxQd3H8+iBJvF0F0MsSAoAtSqMMMLUvi1d5IbHU2Ew0SrNy1TUJ1CRPDi+idKY+watw0yCpYExGtXWzsTQgIDJKxCADVVwogrhziwbL2G5DmI8rTO3G7tZ0SgJkr6uj5thSbMuy0r1trJiWF4lKdqGxKSzGk7KLQkwWyOgaAKinsTCHc6JoqlkXoWzbB08FbLLu16FJdarxWkIA/view)

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/fehann/VisEMAp2020/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
