# Configurações

[:house:](./README.md#readme)

```js
/**
 * Sintaxe.
 */
const piii = new Piii({
  filters: {Array},
  aliases: {Object},
  repeated: {Boolean},
  censor: {String|Function},
  cleaner: {Function}
});
```

(Clique nos *links* abaixo para saber mais.)

* [`filters`](./opcoes/1-filters.md#readme) ― Lista de filtros (não há nada definido por padrão).
* [`aliases`](./opcoes/2-aliases.md#readme) ― Alfabeto alternativo para alguns caracteres.
* [`repeated` ](./opcoes/3-repeated.md#readme) ― Informa se deve ignorar letras repetidas.
* [`censor` ](./opcoes/4-censor.md#readme) ― Valor que substituirá os palavrões dentro da *string*.
* [`cleaner`](./opcoes/5-cleaner.md#readme) ― Removedor de acentos (usa [`diacritics`](https://npm.im/diacritics) por padrão).
