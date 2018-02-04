# Configuração

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

* `filters` ― Lista de filtros (não há nada definido por padrão).
* `aliases` ― Alfabeto alternativo para alguns caracteres.
* `censor` ― Valor que substituirá os palavrões dentro da *string*.
* `cleaner` ― Removedor de acentos (usa [`diacritics`](https://npm.im/diacritics) por padrão).

Depois de aprender a configurá-lo, [veja aqui como usá-lo](./usando.md).