# Configurações

[:house:](./README.md#readme)

```js
/**
 * Sintaxe.
 */
const piii = new Piii({
  filters: {Array},
  aliases: {Object},
  censor: {String|Function},
  cleaner: {Function}
});
```

(Clique nos *links* abaixo para saber mais.)

* [`filters`](./opcoes/1-filters.md#readme) ― Lista de filtros (não há nada definido por padrão).
* [`aliases`](./opcoes/2-aliases.md#readme) ― Alfabeto alternativo para alguns caracteres.
* [`censor` ](./opcoes/3-censor.md#readme) ― Valor que substituirá os palavrões dentro da *string*.
* [`cleaner`](./opcoes/4-cleaner.md#readme) ― Removedor de acentos (usa [`diacritics`](https://npm.im/diacritics) por padrão).
