# Semanttinen HTML5 - Sivun merkityksellinen rakenne

Semanttinen HTML5 auttaa sekä kehittäjiä että selaimia ymmärtämään sivun rakenteen paremmin. Ajattele sitä kuin sanomalehden rakennetta - jokaisella osalla on oma selkeä tarkoituksensa ja paikkansa.

## Rakenteelliset elementit

Nämä elementit ovat kuin rakennuksen eri huoneet - jokaisella on oma tärkeä tehtävänsä:

```html
<header>
    <!-- Sivun yläosa: logo, päävalikko, otsikko -->
    <h1>Yrityksen Nimi</h1>
    <nav>
        <!-- Navigaatio/valikko -->
        <a href="/">Etusivu</a>
        <a href="/palvelut">Palvelut</a>
    </nav>
</header>

<main>
    <!-- Sivun pääsisältö -->
    <article>
        <!-- Itsenäinen sisältökokonaisuus, kuten blogikirjoitus -->
        <h2>Artikkelin otsikko</h2>
        <section>
            <!-- Artikkelin osa/kappale -->
            <h3>Ensimmäinen kappale</h3>
            <p>Tekstiä tässä...</p>
        </section>
    </article>

    <aside>
        <!-- Sivupalkki, lisätiedot -->
        <h3>Lue lisää</h3>
        <p>Aiheeseen liittyvää sisältöä...</p>
    </aside>
</main>

<footer>
    <!-- Sivun alaosa: yhteystiedot, copyright -->
    <p>&copy; 2024 Yritys Oy</p>
</footer>
```

## Figure ja figcaption

Nämä elementit ovat tarkoitettu kuvien, kaavioiden tai muun median ja niiden selitysten esittämiseen:

```html
<figure>
    <img src="kaavio.jpg" alt="Myyntitilasto">
    <figcaption>
        Kuva 1: Yrityksen myynti vuonna 2023 kvartaaleittain
    </figcaption>
</figure>
```

## Time ja address

Nämä elementit auttavat merkitsemään aikaan ja yhteystietoihin liittyvää sisältöä:

```html
<p>Tapahtuma alkaa <time datetime="2024-06-15T18:00">15. kesäkuuta klo 18:00</time></p>

<address>
    Yritys Oy<br>
    Kauppakatu 1<br>
    00100 Helsinki<br>
    <a href="mailto:info@yritys.fi">info@yritys.fi</a>
</address>
```

## Details ja summary

Nämä elementit luovat laajennettavan osion, joka näyttää lisätietoja klikattaessa:

```html
<details>
    <summary>Mikä on HTML5?</summary>
    <p>HTML5 on uusin versio HTML-merkintäkielestä. Se toi mukanaan 
    monia uusia elementtejä, jotka helpottavat sisällön jäsentämistä 
    ja parantavat verkkosivujen saavutettavuutta.</p>
</details>
```

## Merkitykselliset div- ja span-elementit

Vaikka div ja span ovat yleisiä säiliöelementtejä, niille voidaan antaa merkitys custom-attribuuteilla:

```html
<div class="tuotekortti" role="article">
    <h2>Tuotteen nimi</h2>
    <p>Hinta: <span class="hinta">29.99€</span></p>
</div>

<div class="ilmoitus" role="alert">
    <span class="tila">Onnistui!</span>
    Tilaus on vastaanotettu.
</div>
```

## Näiden semanttisten elementtien käyttö:

- Parantaa sivuston saavutettavuutta ruudunlukuohjelmille
- Tekee koodista helpommin ymmärrettävää ja ylläpidettävää
- Auttaa hakukoneita ymmärtämään sivun sisältöä paremmin
- Selkeyttää sivuston rakennetta muille kehittäjille

Muista: Semanttinen HTML ei ole vain koodia - se on tapa kertoa sekä ihmisille että koneille, mitä mikäkin sisältö tarkoittaa ja mikä sen tarkoitus on.
