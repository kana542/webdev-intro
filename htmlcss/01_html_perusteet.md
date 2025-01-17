# HTML - Nettisivujen rakennuspalat

Ajattele HTML:ää kuin talon rakennuspiirustusta. Jokainen elementti on kuin huonekalu tai rakennusosa, jolla on oma tarkoituksensa. Aloitetaan perustuksista!

## Dokumentin perusrakenne

Jokainen nettisivu tarvitsee tietyn perusrakenteen toimiakseen. Se on kuin talon perustus:

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Minun ensimmäinen nettisivu</title>
    </head>
    <body>
        Tänne tulee sivun sisältö!
    </body>
</html>
```

- `<!DOCTYPE html>` kertoo selaimelle, että kyseessä on moderni HTML-sivu
- `<html>` on kuin talon ulkoseinät - kaikki muu tulee sen sisään
- `<head>` sisältää tietoja sivusta, kuten otsikon (`<title>`) - nämä eivät näy itse sivulla
- `<body>` on se osa, jonka käyttäjät näkevät - kaikki näkyvä sisältö tulee tänne

## Tekstin muotoilu

Teksti on nettisivujen peruselementti. HTML tarjoaa useita tapoja sen muotoiluun:

```html
<h1>Tämä on pääotsikko</h1>
<h2>Tämä on alaotsikko</h2>
<p>Tämä on tavallista tekstiä kappaleen sisällä.</p>
<strong>Tämä teksti on lihavoitu</strong> ja <em>tämä on kursivoitu</em>.
```

- Otsikkotasoja on kuusi (h1-h6), missä h1 on suurin ja tärkein. Ajattele niitä kuin kirjan otsikointia: pääotsikko, luvun otsikko, alaluvun otsikko ja niin edelleen.

## Listat

Listoja on kahdenlaisia: järjestettyjä (numeroidut) ja järjestämättömiä (ranskalaiset viivat):

```html
<ul> <!-- järjestämätön lista (unordered list) -->
    <li>Maito</li>
    <li>Leipä</li>
    <li>Juusto</li>
</ul>

<ol> <!-- järjestetty lista (ordered list) -->
    <li>Ensimmäinen vaihe</li>
    <li>Toinen vaihe</li>
    <li>Kolmas vaihe</li>
</ol>
```

## Linkit ja kuvat

Linkit ja kuvat ovat kuin nettisivujen ovet ja ikkunat - ne yhdistävät sivuja toisiinsa ja tuovat visuaalista sisältöä:

```html
<!-- Linkki toiselle sivulle -->
<a href="https://www.esimerkki.fi">Klikkaa tästä</a>

<!-- Kuvan lisääminen -->
<img src="kuva.jpg" alt="Kaunis maisema">
```

- `href` kertoo minne linkki vie, ja `src` kertoo mistä kuva löytyy. `alt`-teksti on tärkeä: se näytetään jos kuva ei lataudu, ja näkövammaiset käyttäjät kuulevat sen ruudunlukuohjelmilla.

## Lomakkeet

Lomakkeet ovat tapa kerätä tietoa käyttäjiltä. Ne ovat kuin paperilomakkeita, mutta digitaalisessa muodossa:

```html
<form>
    <label for="nimi">Nimesi:</label>
    <input type="text" id="nimi" name="nimi">

    <label for="viesti">Viestisi:</label>
    <textarea id="viesti" name="viesti"></textarea>

    <button type="submit">Lähetä</button>
</form>
```

## Taulukot

Taulukot ovat hyödyllisiä, kun haluat esittää tietoa riveissä ja sarakkeissa:

```html
<table>
    <tr> <!-- table row = taulukon rivi -->
        <th>Nimi</th> <!-- table header = otsikkosolu -->
        <th>Ikä</th>
    </tr>
    <tr>
        <td>Matti</td> <!-- table data = tavallinen solu -->
        <td>25</td>
    </tr>
</table>
```

Muista, että jokainen HTML-elementti alkaa avaavalla tagilla (`<elementti>`) ja päättyy sulkevaan tagiin (`</elementti>`). Ne ovat kuin sulkumerkit - jos avaat yhden, muista sulkea se!
