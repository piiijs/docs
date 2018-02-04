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

(Clique nos *links* abaixo para saber mais.)

* [`filters`](./opcoes/1-filters.md) ― Lista de filtros (não há nada definido por padrão).
* [`aliases`](./opcoes/2-aliases.md) ― Alfabeto alternativo para alguns caracteres.
* [`censor` ](./opcoes/3-censor.md)― Valor que substituirá os palavrões dentro da *string*.
* [`cleaner`](./opcoes/4-cleaner.md) ― Removedor de acentos (usa [`diacritics`](https://npm.im/diacritics) por padrão).

---

Depois de aprender a configurá-lo, [veja aqui como usá-lo](./usando.md).
