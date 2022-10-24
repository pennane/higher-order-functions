Ok. Letsego. Tän dokun ideana on tehä tyypeistä 10x devaajia.

"moderni javascript", arrayn sisään rakennetut metodit, for looppei ei tarvi käyttää

## Hyvät videot aiheesta, check em out
[10 min javascript functional programming video liittyen niihi "moderneihin" metodeihin](https://www.youtube.com/watch?v=BMUiFMZr7vk&t=329s&ab_channel=FunFunFunction)

Metodit erikseen:

[Array.map & Array.filter (1min)](https://www.youtube.com/watch?v=D0FzqTWedM0&ab_channel=GoogleChromeDevelopers)

[Array.reduce (0min)](https://www.youtube.com/watch?v=tPGQ6pLuiOI&ab_channel=GoogleChromeDevelopers)

[Array.some & Array.every (1min)](https://www.youtube.com/watch?v=ZCxsknqbuwU&ab_channel=GoogleChromeDevelopers) <- tää on cool, predikaattilogiikka straight outta matikantunti

## Deklaratiivinen ja imperatiivinen ohjelmointi

_Käytännössä_ on olemassa kahdenlaista ohjelmointia: **imperatiivista** ja **deklaratiivista**.

**Imperatiivinen ohjelmointi** on tietokonelle käskyjen latelemista
**Deklaratiivinen ohjelmointi** on tietokoneelta asioiden pyytämistä

Termeinä imperatiivinen ja deklaratiivinen on vähän huuruiset, joten kannattaa lukea koodiesimerkit ajatuksella. Koodi puhuu puolestaan jne

### Imperatiivinen ohjelmointi

Käytännössä kaikki meidän ohjelmointikursseilla koodattu koodi **on ollut imperatiivista**.

Imperatiivisessa ohjelmoinnissa annetaan tietokoneelle käskyjä, jotka ohjelmoijana satutaan tietämään johtavan haluttuun lopputulokseen.

Esimerkiksi, jos halutaan napata listasta kaikki parilliset luvut, voisi ohjelmakoodi näyttää tältä:

```js
const values = [1,2,3,4,5,6]
const evenValues = []
for (const value of values) {
	if (value % 2 === 0) {
		evenValues.push(value)
	}
}
console.log(evenValues);
=> 2,4,6
```

Ratkaisussa luodaan lista, joka käydään lävitse (iteroidaan läpi). Jos iteraation arvo on kahdella jaollinen, se lisätään tulos listaan. Lopulta saadaan uusi lista jossa on vain parillisia arvoja.

### Deklaratiivinen ohjelmointi

Deklaratiivinen ohjelmointi on sitä, että vastoin imperatiivista ohjelmointia pyritään olemaan miettimättä implementaation yksityiskohtia.

Deklaratiivisessa ohjelmoinnissa pyritään luomaan ohjelmakoodia, joka on ihmiselle välittömästi luettavaa.

Aiemman esimerkin ohjelmointi deklaratiivisesti:

```js
const values = [1,2,3,4,5,6]
const evenValues = values.filter(value => isEven(value))
console.log(evenValues);
=> 2,4,6
```

Skädäm. Aika paljon mukavampaa koodia.

Itse ajattelen, että deklaratiivisen ohjelmoinnin pääpointti on, että jos osaa lukea englantia, osaa lukea deklaratiivista koodia.

Esimerkissä arvon tarkastaminen on myöskin viety erilliseen funktioon `isEven`. Tämä mahdollistaa sen, ettei kyseisen funktion implementaatiosta tarvitse välittää, ja koodi on vielä luettavampaa.

isEven funktion implementaatio voi vaikka näyttää tältä

```js
const isEven = (value) => value % 2 === 0
```

#### Higher order functionit

Koodiesimerkissä käytettiin `.filter` metodia. Se on `higher-order funktio`.

**Higher-order funktio** tarkoittaa funktiota, joka **ottaa parametriksi jonkun toisen funktion.**
Esimerkissä `higher-order funktiolle filter` annettiin parametrina `proseduraalinen funktio isEven`

Toinen arrayn higher-order funktio on **.map()**, joka muuttaa listan kaikki arvot proseduraalisen funktion mukaan

Esimerkiksi proseduraalinen funktio joka muuttaa merkkijonon isoiksi merkeiksi:

```js
const toUpperCase = (string) => string.toUpperCase()
```

Sitä voidaan käyttää higher order funktion parametrina

```js
const values = ["a", "b", "c"]
const upperCaseValues = values.map(toUpperCase)
console.log(evenValues);
=> "A", "B", "C"
```

**TL;DR** Higher order funktio = funktio joka ottaa parametrina toisen funktion

Kaikki ne arrayn metodit
`.filter()` `.map()` `.forEach()` `.reduce()` `.flat()` ja `.flatmap()`
ovat higher order funktioita.

Tsekatkaa tubesta
