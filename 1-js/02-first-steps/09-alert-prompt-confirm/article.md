# Interacțiuni: alert, prompt, confirm

În această parte a tutorialului vom acoperi limbajul JavaScript așa cum este, fără modificari ambientale specifice.

Cu toate acestea, vom continua să folosim browserul ca mediu demonstrativ de lucru, așadar ar trebui să cunoaștem cel puțin câteva dintre funcțiile sale pentru interfața utilizatorului. În acest capitol ne vom familiariza cu funcțiile `alert`, `prompt` si `confirm` ale browserului.

## alert

Sintaxă:

```js
alert(mesaj);
```

Această funcție afișează un mesaj și întrerupe execuția scriptului până când utilizatorul apasă "OK".

De exemplu:

```js run
alert("Bună");
```

Mini-fereastra cu acest mesaj este denumită "fereastra formală". Cuvândul "formal" (în acest context) înseamna că vizitatorul nu poate interacționa cu restul paginii, apăsa alte butoane etc până când nu a rezolvat într-un fel sau altul problema cu această fereastră. În acest caz până când nu apasă "OK".

## prompt

Funcția `prompt` acceptă două argumente:

```js no-beautify
result = prompt(titlu, [implicit]);
```

Afișează o fereastră formală cu un mesaj text, un câmp de intrare pentru vizitator și butoanele OK/Anuleaza.

`titlu`
: Textul care va fi afișat vizitatorului.

`implicit`
: Un parametru secundar opțional reprezentând valoarea inițiala pentru câmpul de intrare.

Vizitatorul poate să introducă un text în câmpul prompt și să apese OK. Sau poate să anuleze apăsând butonul Anulare sau apăsând tasta `key:Esc`.

Apelarea funcției `prompt` returnează textul din câmpul de intrare sau `null`, dacă fereastra a fost anulată.

De exemplu:

```js run
let varsta = prompt('Câți ani ai?', 100);

alert(`Ai ${varsta} ani!`); // Ai 100 ani!
```

````warn header="În IE: întotdeauna specificați un `implicit`"
Al doilea parametru este opțional, dar dacă nu îl specificăm, Internet Explorer va insera textul `"undefined"` în câmpul de intrare.

Rulați acest cod în Internet Explorer pentru a vedea:

```js run
let test = prompt("Test");
```

Așadar, pentru ca prompturile să arate bine în IE, vă recomandăm să specificați întotdeauna al doilea argument:

```js run
let test = prompt("Test", ''); // <-- pentru IE
```
````

## confirm

Sintaxa:

```js
rezultat = confirm(intrebare);
```

Funcția `confirm` afișează o fereastră formală cu o `intrebare` și două butoane: OK și Anulează.

Rezultatul este `true` (adevărat) dacă OK este apăsat și `false` (fals) altfel.

De exemplu:

```js run
let esteSef = confirm("Ești tu șeful?");

alert( esteSef ); // true (adevarat) dacă OK este apăsat
```

## Recapitulare

Am acoperit 3 funcții specifice ale browserului prin care se interacționează cu vizitatorii:

`alert`
: afișează un mesaj.

`prompt`
: afișează un mesaj prin care cere utilizatorului să introducă text. Returnează textul sau, dacă butonul Anuleaza sau tasta `key:Esc` este apasată, `null`.

`confirm`
: afișează un mesaj și așteaptă utilizatorul să apese "OK" sau "Anulează". Returnează `true` (adevărat) pentru OK și `false` (fals) pentru Anuleaza/`key:Esc`.

Toate aceste metode sunt formale: ele întrerup execuția scriptului și nu permit vizitatorului să interacționeze cu restul paginii până când fereastra a fost îndepărtată.

Există două limitari împărtașite de toate metodele de mai sus:

1. Locația exactă a ferestrei formale este determinată de browser. În general aceasta este în centru.
2. Aspectul exact al ferestrei formale depinde, de asemenea, de browser. Ea nu poate fi modificată.

Acesta este prețul simplității. Există alte căi pentru a afișa ferestre mai frumoase și mai bogate ca interactivitate, dar dacă "zorzoanele" nu contează atât de mult, aceste metode sunt cât se poate de potrivite.
