# Saavutettavuus ja Hakukoneoptimointi - Tee sivustasi kaikkien saavutettava!

Ajatellaan nettisivua kuin kauppakeskusta. Aivan kuten kauppakeskuksessa tarvitaan selkeitä opasteita, esteettömiä kulkureittejä ja hyvin suunniteltua rakennetta, nettisivuilla tarvitaan vastaavia elementtejä, jotta kaikki käyttäjät ja hakukoneet löytävät etsimänsä.

## ARIA-roolit ja -attribuutit

ARIA (Accessible Rich Internet Applications) on kuin opastejärjestelmä nettisivullasi. Se kertoo ruudunlukuohjelmille ja apuvälineille, mitä mikäkin elementti tekee.

```html
<!-- Esimerkki navigaatiosta -->
<nav role="navigation" aria-label="Päävalikko">
    <ul>
        <li><a href="/" aria-current="page">Etusivu</a></li>
        <li><a href="/tuotteet">Tuotteet</a></li>
    </ul>
</nav>

<!-- Välilehdet -->
<div role="tablist">
    <button role="tab" 
            aria-selected="true" 
            aria-controls="panel1">
        Tiedot
    </button>
    <div role="tabpanel" 
         id="panel1" 
         aria-labelledby="tab1">
        Sisältö tässä...
    </div>
</div>
```

## Kontrastisuhteet

Kontrastisuhde on kuin valojen kirkkauden säätämistä - tekstin täytyy erottua taustasta selkeästi. Tämä auttaa kaikkia käyttäjiä, mutta erityisesti näkövammaisia.

```css
/* Hyvä kontrasti (väh. 4.5:1 normaalille tekstille) */
.teksti {
    /* Tumma teksti vaalealla taustalla */
    color: #333333;        /* Lähes musta */
    background: #FFFFFF;   /* Valkoinen */
}

/* Isompi teksti (yli 18px) tarvitsee vähemmän kontrastia (3:1) */
.otsikko {
    color: #767676;        /* Harmaa */
    background: #FFFFFF;   /* Valkoinen */
    font-size: 24px;
}
```

## Näppäimistökäytettävyys

Näppäimistökäytettävyys on kuin rakennuksen esteettömyysreitit - kaikkien elementtien pitää olla saavutettavissa ilman hiirtä.

```css
/* Selkeä fokus-tila linkeille ja painikkeille */
a:focus,
button:focus {
    outline: 3px solid #4CAF50;
    outline-offset: 2px;
}

/* Interaktiiviset elementit */
.nappi {
    cursor: pointer;
    padding: 10px;

    /* Varmista riittävä klikkialue */
    min-height: 44px;
    min-width: 44px;
}
```

## Semanttinen HTML SEO:ta varten

Semanttinen HTML on kuin rakennuksen pohjapiirustus - se kertoo hakukoneille sivusi rakenteen ja sisällön merkityksen.

```html
<!DOCTYPE html>
<html lang="fi">
<head>
    <title>Yrityksen Nimi - Palvelut</title>
    <meta name="description" content="Kuvaus palveluistamme">
</head>
<body>
    <header>
        <h1>Palvelumme</h1>
        <nav><!-- Navigaatio tähän --></nav>
    </header>
    
    <main>
        <article>
            <h2>Verkkopalvelut</h2>
            <section>
                <h3>Verkkosivut</h3>
                <p>Kuvaus verkkosivupalveluista...</p>
            </section>
        </article>
    </main>
    
    <footer>
        <address>Yhteystiedot tähän</address>
    </footer>
</body>
</html>
```

## Meta-tagit ja sosiaalisen median tagit

Meta-tagit ovat kuin kirjan takakannen teksti - ne kertovat hakukoneille ja sosiaaliselle medialle, mistä sivullasi on kyse.

```html
<head>
    <!-- Perus meta-tagit -->
    <meta charset="UTF-8">
    <meta name="description" content="Lyhyt kuvaus sivustosta">
    <meta name="keywords" content="avainsana1, avainsana2">
    
    <!-- Open Graph -tagit (Facebook, LinkedIn) -->
    <meta property="og:title" content="Sivun otsikko">
    <meta property="og:description" content="Sivun kuvaus">
    <meta property="og:image" content="kuva.jpg">
    
    <!-- Twitter Card -tagit -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Sivun otsikko">
</head>
```

## Sivukartat ja robots.txt

Sivukartta ja robots.txt ovat kuin opaskartta ja ohjeet hakukoneille.

```txt
# robots.txt
User-agent: *
Allow: /
Disallow: /admin/
Sitemap: https://www.sivusto.fi/sitemap.xml
```

```xml
<!-- sitemap.xml -->
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
    <url>
        <loc>https://www.sivusto.fi/</loc>
        <lastmod>2024-01-14</lastmod>
        <changefreq>weekly</changefreq>
        <priority>1.0</priority>
    </url>
</urlset>
