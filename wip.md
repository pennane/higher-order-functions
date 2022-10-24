`.filter()` `.map()` `.forEach()` `.reduce()` `.flat()` ja `.flatmap()` [array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) tietorakenteeseen sisäänrakennettuja metodeja, joiden avulla voi kirjoittaa deklaratiivista koodia.

Mikä näitä metodeja yhdistää on se, että ne kaikki **käyvät listan elementit läpi**, ja **muuntaa arvot joksikin uudeksi listaksi**.

Näillä metodeilla voidaan korvata `for loopin` käyttö käytännössä kokonaan.

### `.filter()` valikoi predikaattifunktion avulla listasta osajoukon

[.filter() mdn dokumentaatio](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

```js
const values = ["a", "b", "c"]
const valuesWithoutA = values.filter(value => value !== "a")
console.log(valuesWithoutA);
=> "B", "C"
```

tai vaikka se kuuluisa parillinen check

```js
const values = [1,2,3,4,5,6,7,8]
const evenValues = values.filter(value => value % 2 === 0)
console.log(evenValues);
=> 3,4,6,8
```

### `.map()` muokkaa jokaista listan arvoa

[.map() mdn dokumentaatio](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

```js
const values = ["a", "b", "c"]
const upperCaseValues = values.map(value => value.toUpperCase())
console.log(upperCaseValues);
=> "A", "B", "C"
```

### `.forEach()` perus for loop. tätä ei tarvitse juurikaan käyttää.

[.forEach() mdn dokumentaatio](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
forEach on käytännössä vain for loopin raaka vastine. forEach ei palauta mitään uutta arvoa, vaan käy vain listan läpi

```js
const values = ["a", "b", "c"]
const upperCaseValues = values.forEach(value => value.toUpperCase())
console.log(upperCaseValues);
=> undefined
console.log(values)
=> "a", "b", "c"
```

### `.reduce()` muuntaa listan yhdeksi arvoksi

[.reduce() mdn dokumentaatio](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)

Reduce on psykoosi funktio. Sillä on kiva kikkailla, mutta sillä saa helposti aikaan vaikeasti luettavaa koodia.
Esimerkki reducella laskettavasta summasta

```js
const values = [1,2,3]
const sum = values.reduce((combined, value) => combined + value)
console.log(sum)
=> 6
```
