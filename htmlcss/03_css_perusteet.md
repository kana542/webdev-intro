# CSS - Tyylien maailma verkkosivuilla

CSS (Cascading Style Sheets) on kieli, jolla teemme verkkosivuista kauniita ja käyttäjäystävällisiä. Ajattele CSS:ää kuin taiteilijaa, joka maalaa ja muotoilee HTML:n luoman rakenteen.

## Syntaksi ja perussäännöt

CSS:n kielioppi on yksinkertainen mutta tarkka. Se koostuu valitsimista (selectors) ja määrityksistä (declarations):

```css
/* Perusrakenne */
valitsin {
    ominaisuus: arvo;
    toinen-ominaisuus: toinen-arvo;
}

/* Käytännön esimerkki */
p {
    color: blue;            /* Tekstin väri */
    font-size: 16px;       /* Tekstin koko */
    margin-bottom: 20px;   /* Alapuolinen marginaali */
}
```

Voit valita elementtejä monella tavalla:

```css
/* Elementti suoraan */
p { color: blue; }

/* Luokan avulla */
.otsikko { font-size: 24px; }

/* ID:n avulla */
#paavalikko { background: gray; }

/* Sisäkkäiset elementit */
article p { line-height: 1.6; }
```

## Värit ja taustat

CSS tarjoaa monia tapoja määritellä värejä ja taustoja:

```css
.elementti {
    /* Värien eri esitystavat */
    color: red;                     /* Värin nimi */
    background-color: #FF5733;      /* Heksadesimaaliarvo */
    border-color: rgb(255,0,0);     /* RGB-arvo */
    box-shadow: rgba(0,0,0,0.5);    /* RGBA (läpinäkyvyydellä) */

    /* Taustat */
    background-image: url('tausta.jpg');
    background-repeat: no-repeat;    /* Ei toistoa */
    background-position: center;     /* Keskitetty */
    background-size: cover;          /* Täyttää koko alueen */
}
```

## Tekstin muotoilu ja typografia

Tekstin ulkoasua voi muokata monipuolisesti:

```css
.teksti {
    font-family: Arial, sans-serif;  /* Fontti ja varafontti */
    font-size: 16px;                 /* Tekstin koko */
    font-weight: bold;               /* Tekstin paksuus */
    font-style: italic;              /* Tekstin tyyli */
    text-align: center;              /* Tekstin tasaus */
    line-height: 1.5;                /* Riviväli */
    text-decoration: underline;      /* Alleviivaus */
    text-transform: uppercase;       /* Muuntaa isoiksi kirjaimiksi */
    letter-spacing: 2px;             /* Kirjainväli */
}
```

## Reunukset ja varjot

Elementtien ympärille voi lisätä reunuksia ja varjoja:

```css
.laatikko {
    /* Reunukset */
    border: 2px solid black;         /* Kaikki reunat */
    border-radius: 10px;             /* Pyöristetyt kulmat */
    
    /* Marginaalit ja täytteet */
    margin: 20px;                    /* Ulkopuolinen tila */
    padding: 15px;                   /* Sisäpuolinen tila */
    
    /* Varjot */
    box-shadow: 5px 5px 10px gray;   /* Laatikon varjo */
    text-shadow: 2px 2px 4px black;  /* Tekstin varjo */
}
```

## Kuvien käsittely

Kuvia voi muokata monin tavoin CSS:n avulla:

```css
.kuva {
    width: 300px;                    /* Leveys */
    height: auto;                    /* Korkeus suhteessa leveyteen */
    object-fit: cover;               /* Kuvan sovitus */
    border-radius: 50%;              /* Pyöreä kuva */
    opacity: 0.8;                    /* Läpinäkyvyys */
    filter: grayscale(100%);         /* Mustavalkoinen */
}
```

## Pseudoluokat ja pseudoelementit

Nämä mahdollistavat elementtien muokkaamisen eri tiloissa tai lisäsisällön luomisen:

```css
/* Pseudoluokat - elementin tila */
.linkki:hover {                      /* Hiiri linkin päällä */
    color: red;
    text-decoration: none;
}

.painike:active {                    /* Painiketta painetaan */
    background-color: darkblue;
}

.kentta:focus {                      /* Kenttä on valittuna */
    border-color: blue;
}

/* Pseudoelementit - lisäsisältö */
.otsikko::before {                   /* Sisältöä ennen */
    content: "♦ ";
    color: red;
}

.lainaus::after {                    /* Sisältöä jälkeen */
    content: " »";
}

p::first-letter {                    /* Ensimmäinen kirjain */
    font-size: 200%;
    color: darkred;
}
```

CSS:n voima tulee sen monipuolisuudesta ja kerroksellisuudesta. Voit yhdistellä eri ominaisuuksia ja luoda niistä juuri sellaisen kokonaisuuden kuin haluat. Muista, että tyylien testaaminen ja kokeileminen on paras tapa oppia!
