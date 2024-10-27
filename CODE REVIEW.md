# Code Review deste Projeto

# Mochileiros On-line
 
 **Feito por**
Luiz Felipe Campos de Morais


---

**Projeto original por**
Gabriel Henrique Miranda Rodrigues

---

_Curso de Engenharia de Software, Campus Coração Eucarístico_

_Instituto de Informática e Ciências Exatas – Pontifícia Universidade Católica de Minas Gerais (PUC MINAS), Belo Horizonte – MG – Brasil_

---

---
 

##  Arquitetura

Eu sugeriria a divisão de arquivos por pastas, que permite que você adicione novos módulos ou componentes sem se preocupar em misturar códigos. Por exemplo, uma estrutura mínima:

index.html
css/ (com arquivos de estilo, como style.css)
js/ (com arquivos de scripts, como app.js)
assets/

Dessa forma, facilitaria mais a manutenção e a adição de novas funcionalidades no sistema.

### Código inutilizado ou mal definido

Percebe-se que na pasta do projeto, existem muitos arquivos que não estão sendo utilizados e/ou estão com nomes que não definem o que estão realizando: ex: teste.html, teste.css.

Para manutenção de código, sugeriria mudanças no arquivo SegurancaUsuario.js por exemplo:
A função show é responsável por renderizar a tabela, mas a estrutura está sendo definida diretamente dentro dela, o que pode dificultar a manutenção.

Verifique se o backend está esperando tipo_denuncia ou tipoDenuncia para evitar inconsistências entre o front-end e o back-end. Recomendo manter um padrão para o nome dos campos.

Há código duplicado ao definir os valores dos campos e limpar o formulário. Para reduzir a repetição, crie uma função clearForm para limpar os campos, e uma função getFormValues para obter os valores.

Considerando que fetch pode lançar erros, inclua um try/catch na função getAPI.
