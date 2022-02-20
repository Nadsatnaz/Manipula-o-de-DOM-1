# Conceitos Estudados

### **Document.QuerySelector**

Retorna o primeiro elemento dentro do documento (usando ordenação em profundidade, pré-ordenada e transversal dos nós do documento) que corresponde ao grupo especificado de seletores.

```jsx
*element* = document.querySelector(*selectors*);
```

### Element.querySelector()

Retorna o primeiro elemento descendente do elemento em que a função foi invocada e que corresponde aos seletores especificado.

```jsx
elemento = elementoBase.querySelector(seletores);
```

### **Document.querySelectorAll()**

Retorna uma lista de elementos presentes no documento (usando ordenação em profundidade, pré-ordenada e transversal dos nós do documento) que coincidam com o grupo de seletores especificado. O objeto retornado é uma `[NodeList](https://developer.mozilla.org/pt-BR/docs/Web/API/NodeList)`

> Retorna uma lista de elementos presentes no documento (usando ordenação em profundidade, pré-ordenada e transversal dos nós do documento) que coincidam com o grupo de seletores especificado. O objeto retornado é uma `[NodeList](https://developer.mozilla.org/pt-BR/docs/Web/API/NodeList)`
.
> 

---

### **Event.preventDefault()**

Previne o comportamento default do objeto, ou seja cancela o comportamento que os elementos geralmente tem na página, então se o comportamento padrão de um link é abrir um site, nós vamos cancelar isso.

## Event.target

A propriedade **`event.target`** pode ser usada para implementar a delegação de eventos.

```jsx
// Assumindo que existe uma variável 'list' contendo uma instância de um elemento ul de HTML.
function hide(e) {
  // A menos que os itens da lista sejam separados por uma margem, e.target deve ser diferente de e.currentTarget
  e.target.style.visibility = 'hidden';
}

list.addEventListener('click', hide, false);

// Se algum elemento (elemento <li> ou um link dentro de um elemento <li> por exemplo) for clicado, ele desaparecerá.
// Só requer um único listener para fazer isso.
```

### addEventListener

O método JavaScript addEventListener () permite configurar funções a serem chamadas quando um evento especificado acontece, como quando um usuário clica em um botão.

---

### innerHTML

O método JavaScript addEventListener () permite configurar funções a serem chamadas quando um evento especificado acontece, como quando um usuário clica em um botão.

**Sintaxe**

```
var content =element.innerHTML;
```

No retorno, `content` contém o código HTML serializado descrevendo todos os descendentes dos elementos.

```
 element.innerHTML = content;
```

Remove todos os elementos filhos, analisa o conteúdo da string e atribui os nós resultantes como filhos do elemento.

```jsx
// HTML:
// <div id="d"><p>Content</p>
// <p>Further Elaborated</p>
// </div>

const d = document.getElementById("d");
dump(d.innerHTML);

//  a string "<p>Content</p><p>Further Elaborated</p>"
// é exibida na janela do console
```

### **Document.createElement()**

Em um documento [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML), o método **`Document.createElement()`** cria o elemento HTML especificado.

## **Sintaxe**

```jsx
varelemento =document.createElement(nomeDaTag);

```

- `elemento` é o objeto `[Element](https://developer.mozilla.org/pt-BR/docs/Web/API/Element)` criado.
- `nomeDaTag` é uma *string* que especifica o tipo do elemento a ser criado. O `[nodeName` (en-US)](https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeName) do elemento criado é inicializado com o valor da `nomeDaTag`. Não use nomes qualificados (como "html:a") com este método.

Este código cria uma nova `<div>` e a insere antes do elemento com ID "`div1`":

### [HTML](https://developer.mozilla.org/pt-BR/docs/Web/API/Document/createElement#html)

```jsx
<!DOCTYPE html>
<html>
<head>
  <title>||Trabalhando com elementos||</title>
</head>
<body>
  <div id="div1">O texto acima foi criado dinamicamente.</div>
</body>
</html>
```

**Javascript:**

```jsx
**document.body.onload = adcElemento;

function adcElemento () {
  // cria um novo elemento div
  // e dá à ele conteúdo
  var divNova = document.createElement("div");
  var conteudoNovo = document.createTextNode("Olá, cumprimentos!");
  divNova.appendChild(conteudoNovo); //adiciona o nó de texto à nova div criada

  // adiciona o novo elemento criado e seu conteúdo ao DOM
  var divAtual = document.getElementById("div1");
  document.body.insertBefore(divNova, divAtual);
}**
```

### **Element.classList**

O **Element.classList** é uma propriedade somente leitura que retorna uma coleção `[DOMTokenList](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList)` ativa dos atributos de classe do elemento.

- **add( String [, String] )**
Adicione valores de classe especificados. Se essas classes já existem no atributo do elemento, elas são ignoradas.
- **remove( String [,String] )**
Remover valores de classe específicos.
- **item ( Number )**
Retorna o valor da classe por índice na coleção.
- **toggle ( String [, force] )**
Quando apenas um argumento está presente: Toggle class value; Ou seja, se a classe existir, em seguida, removê-lo e retornar false, se não, então adicioná-lo e retornar true. Quando um segundo argumento está presente: Se o segundo argumento é avaliado como true, adicione o valor especificado da classe e, se ele for avaliado como false, remova-o.
- **contains( String )**
Verifica se o valor da classe especificado existe no atributo de classe do elemento.

### Parent.Element

A propriedade parentElement retorna o elemento pai do elemento especificado.

A diferença entre parentElement e [parentNode](https://www.w3schools.com/jsref/prop_node_parentnode.asp), é que parentElement retorna *nulo* se o nó pai não for um nó de elemento:

document.body.parentNode; // Returns the <html> elementdocument.body.parentElement; // Returns the <html> elementdocument.documentElement.parentNode; // Returns the Document nodedocument.documentElement.parentElement; // Returns null (<html> does not have a parent ELEMENT node)

Na maioria dos casos, não importa qual propriedade você usa, no entanto, o parentNode é provavelmente o mais popular.

### appendChild

Adiciona um nó ao final da lista de filhos de um nó pai especificado. Se o nó já existir no documento, ele é removido de seu nó pai atual antes de ser adicionado ao novo pai.

Append an item to a list:

```jsx
const node = document.createElement("li");
const textnode = document.createTextNode("Water");
node.appendChild(textnode);
document.getElementById("myList").appendChild(node);
```

Antes:

- Coffee
- Tea

Depois:

- Coffee
- Tea
- Water
