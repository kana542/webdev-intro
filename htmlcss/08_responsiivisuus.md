# Responsiivinen web-suunnittelu - Sivut jotka toimivat kaikilla laitteilla

Responsiivinen suunnittelu tarkoittaa verkkosivujen rakentamista niin, että ne mukautuvat automaattisesti eri näyttökokoihin. Ajattele sitä kuin veteen kaadettua nestettä - se mukautuu aina astian muotoon täydellisesti.

## Viewport ja meta tag

Mobiililaitteiden oikean skaalauksen varmistaminen:

```html
<!-- Lisää tämä head-osioon -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Tämä meta-tagi kertoo mobiililaitteille, että sivu on suunniteltu responsiiviseksi. Se on kuin kartan mittakaava - ilman sitä mobiililaite ei tiedä miten näyttää sivu oikein.

## Media Queries

Media queryjen avulla voimme määritellä eri tyylejä eri näyttöko'oille:

```css
/* Perustyylit (mobile-first) */
.container {
    width: 100%;
    padding: 10px;
}

/* Tyylit tableteille */
@media screen and (min-width: 768px) {
    .container {
        width: 750px;
        margin: 0 auto;
    }
}

/* Tyylit tietokoneille */
@media screen and (min-width: 1024px) {
    .container {
        width: 960px;
    }
}

/* Voidaan myös tarkistaa näytön orientaatio */
@media screen and (orientation: landscape) {
    /* Tyylit vaakasuuntaiselle näytölle */
}
```

## Responsiiviset yksiköt

Suhteelliset yksiköt auttavat sisällön skaalaamisessa:

```css
.elementti {
    /* Prosentit - suhteessa vanhempaan */
    width: 50%;              /* Puolet vanhemman leveydestä */
    margin: 5%;             /* Marginaali suhteessa vanhempaan */
    
    /* Viewport-yksiköt */
    height: 100vh;          /* 100% viewportin korkeudesta */
    width: 50vw;           /* 50% viewportin leveydestä */
    
    /* Em - suhteessa elementin fonttikokoon */
    padding: 1.5em;        /* 1.5 kertaa elementin fonttikoko */
    margin: 2em;           /* 2 kertaa elementin fonttikoko */
    
    /* Rem - suhteessa juurielementin fonttikokoon */
    font-size: 1.2rem;     /* 1.2 kertaa html-elementin fonttikoko */
    padding: 2rem;         /* 2 kertaa html-elementin fonttikoko */
}

/* Juurielementin fonttikoko (oletusarvo selaimissa on 16px) */
html {
    font-size: 16px;
}
```

## Mobile-first suunnittelu

Mobile-first tarkoittaa suunnittelua ensin mobiililaitteille:

```css
/* Perustyylit mobiilille */
.navigaatio {
    padding: 10px;
}

/* Lisätään toiminnallisuutta isommille näytöille */
@media screen and (min-width: 768px) {
    .navigaatio {
        display: flex;
        justify-content: space-between;
    }
}

/* Vielä lisää toiminnallisuutta tietokoneille */
@media screen and (min-width: 1024px) {
    .navigaatio {
        padding: 20px;
        max-width: 1200px;
        margin: 0 auto;
    }
}
```

## Kuvien skaalaus

Kuvien responsiivinen käsittely:

```css
/* Perusohje responsiivisille kuville */
img {
    max-width: 100%;     /* Ei koskaan leveämpi kuin vanhempi */
    height: auto;        /* Säilyttää kuvasuhteen */
}

/* Modernimpi tapa kuville */
.kuva-container {
    width: 100%;
    height: 300px;      /* Kiinteä korkeus containerille */
}

.kuva-container img {
    width: 100%;
    height: 100%;
    object-fit: cover;   /* Täyttää tilan säilyttäen kuvasuhteen */
    object-position: center; /* Keskittää kuvan */
}

/* Eri kokoiset kuvat eri näyttöko'oille */
picture {
    width: 100%;
}

/* HTML:ssä:
<picture>
    <source media="(min-width: 1024px)" srcset="iso-kuva.jpg">
    <source media="(min-width: 768px)" srcset="keskikokoinen-kuva.jpg">
    <img src="pieni-kuva.jpg" alt="Kuvaus">
</picture>
*/
```

## Responsiivinen typografia

Tekstin koon mukautuminen näyttökoon mukaan:

```css
/* Perusfonttikoko */
html {
    font-size: 16px;
}

/* Skaalautuva otsikko */
h1 {
    font-size: calc(1.5rem + 2vw);  /* Yhdistää kiinteän ja skaalautuvan koon */
    line-height: 1.2;               /* Suhteellinen riviväli */
}

/* Mukautuva tekstin koko media queryjen avulla */
p {
    font-size: 1rem;      /* Peruskoko mobiilille */
}

@media screen and (min-width: 768px) {
    p {
        font-size: 1.1rem;
    }
}

@media screen and (min-width: 1024px) {
    p {
        font-size: 1.2rem;
    }
}
```

## Tärkeimmät periaatteet responsiivisessa suunnittelussa:

- Aloita mobiilista ja lisää toiminnallisuutta isommille näytöille
- Käytä suhteellisia yksiköitä kiinteiden sijaan
- Media queryt ovat työkalusi eri näyttökokojen hallintaan
- Viewport meta-tagi on välttämätön mobiililaitteilla
- Testaa sivua erilaisilla laitteilla ja näyttöko'oilla
