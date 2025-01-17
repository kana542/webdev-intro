# CSS Valitsimet - Miten löydämme muokattavat elementit

CSS-valitsimet ovat kuin tarkkoja osoitteita, joiden avulla kerromme selaimelle mihin elementteihin haluamme tyylit kohdistaa. Oikeiden valitsimien käyttö on avain tehokkaaseen ja ylläpidettävään tyylien hallintaan.

## Perusvalitsimet

Yksinkertaisimmat tavat valita elementtejä:

```css
/* Elementtivalitsin - valitsee KAIKKI p-elementit */
p {
    color: blue;
}

/* Luokkavalitsin - valitsee elementit, joilla on luokka "otsikko" */
.otsikko {
    font-size: 24px;
}

/* ID-valitsin - valitsee elementin, jonka ID on "paavalikko" */
#paavalikko {
    background-color: gray;
}
```

## Yhdistelmävalitsimet

Voimme yhdistää valitsimia tarkempaa kohdistusta varten:

```css
/* Elementti JA luokka */
p.korostettu {
    background-color: yellow;    /* Vaikuttaa vain p-elementteihin, joilla on luokka "korostettu" */
}

/* Useampi luokka */
.painike.aktiivinen {
    background-color: green;     /* Elementit, joilla on MOLEMMAT luokat */
}

/* Ryhmävalitsin */
h1, h2, h3 {
    font-family: Arial;         /* Sama tyyli usealle valitsimelle */
}
```

## Attribuuttivalitsimet

Voimme valita elementtejä niiden attribuuttien perusteella:

```css
/* Elementit, joilla on tietty attribuutti */
[title] {
    cursor: help;
}

/* Tarkka attribuutin arvo */
[type="submit"] {
    background-color: blue;
}

/* Attribuutti, joka alkaa tietyllä tekstillä */
[href^="https"] {
    color: green;              /* Kaikki https-linkit */
}

/* Attribuutti, joka päättyy tiettyyn tekstiin */
[src$=".pdf"] {
    background-image: url('pdf-icon.png');
}
```

## Sisarusvalitsimet

Näillä valitsemme elementtejä niiden keskinäisten suhteiden perusteella:

```css
/* Seuraava sisar (+) */
h2 + p {
    font-weight: bold;        /* p-elementti, joka tulee heti h2:n jälkeen */
}

/* Kaikki seuraavat sisaret (~) */
h2 ~ p {
    margin-left: 20px;        /* Kaikki p-elementit h2:n jälkeen */
}
```

## Lapsi- ja jälkeläisvalitsimet

Elementtien hierarkian hyödyntäminen:

```css
/* Jälkeläisvalitsin (välilyönti) */
article p {
    line-height: 1.6;         /* Kaikki p-elementit article-elementin sisällä */
}

/* Suora lapsi (>) */
section > p {
    margin: 10px;             /* Vain suorat lapsi-p-elementit */
}

/* Monitasoinen valinta */
nav > ul > li a {
    text-decoration: none;     /* Linkit navigaation listassa */
}
```

## Specificity (täsmällisyys)

CSS-sääntöjen täsmällisyys määrää, mikä tyyli voittaa ristiriitatilanteissa:

```css
/* Nouseva täsmällisyys */
p {
    color: blue;              /* Täsmällisyys: 0,0,0,1 */
}

.teksti {
    color: red;               /* Täsmällisyys: 0,0,1,0 */
}

#erityinen {
    color: green;             /* Täsmällisyys: 0,1,0,0 */
}

/* !important ylittää kaikki */
p {
    color: purple !important; /* Vältä käyttämästä, ellei pakko */
}
```

### Täsmällisyyden laskeminen

- Inline-tyylit: 1,0,0,0
- ID: 0,1,0,0
- Luokat ja attribuutit: 0,0,1,0
- Elementit: 0,0,0,1

### Muista:

- Käytä mahdollisimman yksinkertaisia valitsimia
- Suosi luokkia ID:iden sijaan
- Vältä !important-määrettä
- Pidä valitsimet selkeinä ja ymmärrettävinä
- Mieti hierarkiaa ja elementtien suhteita

Hyvät valitsimet tekevät CSS:stä helpommin ylläpidettävää ja muokattavaa. Ne ovat kuin hyvä järjestelmä kirjastossa - kun tiedät tarkan sijainnin, löydät aina etsimäsi!
