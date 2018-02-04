# Configurações

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

(Clique nos *links* abaixo para ver mais sobre.)

* [`filters`](./opcoes/filters.md) ― Lista de filtros (não há nada definido por padrão).
* [`aliases`](./opcoes/aliases.md) ― Alfabeto alternativo para alguns caracteres.
* [`censor` ](./opcoes/censor.md)― Valor que substituirá os palavrões dentro da *string*.
* [`cleaner`](./opcoes/cleaner.md) ― Removedor de acentos (usa [`diacritics`](https://npm.im/diacritics) por padrão).

---

Depois de aprender a configurá-lo, [veja aqui como usá-lo](./usando.md).
