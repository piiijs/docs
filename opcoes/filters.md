# Opção `filters`

> Lista de filtros.

* Tipo: *Array*.
* Valor padrão: `[]`.

Isso deve ser uma *array* contendo todos os filtros que serão usados. Por padrão nenhum filtro é adicionado ― pois existem algumas palavras que não são vistas como de baixo-calão por todas as pessoas ou para determinadas situações ―, portanto, você terá que criar o seu próprio filtro ou obter um de terceiros.

```js
/**
 * Sintaxe.
 */
const piii = new Piii({
  filters: [
     // todos os filtros aqui...
  ]
});
```

## Criando filtros

Para a criação de filtros, é usado *arrays* que posteriormente serão convertidas em *regexs*.

Exemplo simples de filtro:

```js
["foo", "bar"]
```

O *Piii.js* interpretará a *array* acima como `(foo|bar)`, portanto, com esse filtro será obtido todas as ocorrências de *foo* e *bar* denttro de uma *string*. Veja o exemplo:

```js
const filtro = ["foo", "bar"];

const piii = new Piii({
  filters: [
    filtro
  ]
});

piii.filter("foo bar baz") // "* * bar"
```

> **Obs.**: Tudo dentro do filtro deve ser *arrays* e *strings* e as *strings* DEVEM corresponder a expressão regular `/^[a-zA-Z]+$/`, ou seja, só podem ter letras (sem acentos) ― um erro será lançado caso isso não seja seguido.

Algumas regras do interpretador de filtros.

* Uma *string* retorna apenas uma string.
* Uma *array* de *strings* retorna-as como alternação.
* Uma *array* de *arrays* retorna-as como alternação.
* Uma *array* de *string* e *array* retorna-as como continuação.

Exemplos de cada uma das regras:

```js
"foo" // é como "foo"
["foo", "bar"] // é como "(foo|bar)"
[["foo", "bar"], ["foo", "bar"]] // é como "((foo|bar)|(foo|bar))"
["foo", ["bar", "baz"]] // é como "(foo(bar|baz))"
```


## Exemplos

Suponhando que você queira criar um filtro para *merda*.

Você pode fazer algo como:

```js
const filtroDeExemplo = [
  "merd",
  [
    "a",
    "inha",
    "ao"
  ]
];

const piii = new Piii({
  filters: [
    filtroDeExemplo
  ]
});

// exemplos:
piii.filter("Que merda!"); // "Que *!"
piii.filter("Que merdinha!"); // "Que *!"
piii.filter("Que merdão!"); // "Que *!"
```

## Usando filtros de terceiros

Você também pode importar filtros de terceiros para usar. Pesquise no GitHub por [`topic:piii-filter`](https://git.io/vNxcW) para encontrar filtros (caso você crie seu próprio filtro poderá adicionar o *topic* *piii-filter* no repositório para que ele seja facilmente encontrado).

Um filtro já pronto para você começar com *Piii.js* é o [`piii-filters`](ghub.io/piii-filters) que já vem com a filtragem de alguns dos palavrões mais usados na língua portuguesa (e visto como de baixo-calão por quase todos).

Você pode instalá-lo com:

```
npm install --save-dev piii-filters
```

E usá-lo com:

```js
const Piii = require("piii");
const piiiFilters = require("piii-filters");

const piii = Piii({
  filters: [
    ...Object.values(piiiFilters)
  ]
});

piii.filter("Vá se foder!"); // "Vá se *!"
