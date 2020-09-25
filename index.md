# Visualização da Informação - Fernando Hannaka

Este trabalho faz parte do curso de Visualização da Informação do EMAp da FGV.

You can use the [editor on GitHub](https://github.com/fehann/VisEMAp2020/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

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



```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)

```

[Open the Chart in the Vega Editor](https://vega.github.io/editor/#/url/vega-lite/N4Igxg9gdgZglgcxALlANzgUwO4tJKAFzigFcJSBnAdTgBNCALFAFgAY2AacaYsiygAlMiRoRQBmDgF9p3OgENCCvCCgKAtphQhFygLQAOQwCZDEgEZ0TARgCsdiZkMw7Nm+YCcmMGBsKAdkMLBxMQORANBQAnAGtVQgBPAAdtZHA4aLAAG21uSjgALzSANjYIzChIOhIkVB5siGiElLS1CA0SBWyQbnhMbLodAGElTAQmxPDuQggIbOJklABtUCTUnSgOrp6+rEGRsYnoqbk11p0AR1IFIjhlYjQ8kH6D9IAPafON9Ovb4gecCevRe+yG6VOAF1uJ96us2n87oDgXsBuCQJ8IlM4RdfjckUogc9XujThFKAMfMRoKoKbkwLNomw7CUWj8QAUoAhciCSZQViBRoRxpMQJDZNwACSUMCMTBRHRiQjJSjIAD0aqeCAUADoEPdGKQLDq4BA1TK5VFNeMFPpsvdMJqWDrDDqbDqAFaUGnyJQKCmEfn1PS24xmSzWeyOZyudxeHx+QLBUIrUBCkUnHQASRBsJsXBA2NdbBYZ0FR1F6RzMJQhm42JKOs8djL6eO2JA1YxKBsEnrKACOrshlbFczVdzKE8-eQrsMNlHwvb2cnyHcM9dEgki4zHa7eZYM88TZKO+XE5ryBKM8HJlLnDTY73q8PhdYOpMp4f5aXlc7q5sEwZ3zF170fX9x3-S8AhnZ1TDPP99xQOwZzsHUShHb820QpC1wLbFjxsMCf13bNcLrN9ZzdYjsMgrNcN7DcdQCGinzI1dp0o10AgCBC6IYmwjw-L9wNIqsGNfIs3T4vdcOvSjG17GT2MvSTJGkrC2PEgCgMowjt00iDZNXGDKNvESSPPTtcJQyjnRY5TxIY-CBx1FgLNo2TyJnRseMc6yGL7SjAOY1ijLI3DOOxQd3H8+iBJvF0F0MsSAoAtSqMMMLUvi1d5IbHU2Ew0SrNy1TUJ1CRPDi+idKY+watw0yCpYExGtXWzsTQgIDJKxCADVVwogrhziwbL2G5DmI8rTO3G7tZ0SgJkr6uj5thSbMuy0r1trJiWF4lKdqGxKSzGk7KLQkwWyOgaAKinsTCHc6JoqlkXoWzbB08FbLLu16FJdarxWkIA/view)

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/fehann/VisEMAp2020/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
