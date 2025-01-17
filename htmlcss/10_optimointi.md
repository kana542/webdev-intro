# Nettisivujen Suorituskyky ja Optimointi - Tehdään sivustasi tehokkaampi!

Ajatellaan nettisivu kuin ravintolaa. Aivan kuten ravintolassa tarvitset hyvän keittiön organisoinnin, selkeät reseptit ja tehokkaat työskentelytavat, nettisivut tarvitsevat samanlaista huolenpitoa. Katsotaan, miten voimme tehdä nettisivustasi nopeamman ja helpommin ylläpidettävän.

## CSS-tiedostojen organisointi

Kuvittele keittiö, jossa kaikki välineet ovat sikin sokin kaapeissa. Se olisi painajainen, eikö? Sama pätee CSS-tiedostoihin. Hyvä organisointi tekee koodistasi selkeämpää ja helpommin löydettävää.

```
│
├── base/               // Perustyylit
│   ├── _reset.css     // Tyylien nollaus
│   ├── _typography.css // Tekstin tyylit
│   └── _colors.css    // Värimäärittelyt
│
├── components/         // Uudelleenkäytettävät palaset
│   ├── _buttons.css   // Painikkeet
│   ├── _cards.css     // Korttielementit
│   └── _forms.css     // Lomakkeet
│
└── pages/             // Sivukohtaiset tyylit
    ├── _home.css      // Etusivu
    └── _contact.css   // Yhteystiedot
```

On kuitenkin hyvää pitää käytäntönä, ettei luo liikaa tiedostoja. Pienissä projekteissa yksi tiedosto riittää hyvin, mutta isommissa projekteissa voi käyttää useampaa.

## Nimeämiskäytännöt (BEM)

BEM (Block, Element, Modifier) on kuin resepti, joka kertoo tarkalleen, miten nimetä CSS-luokkasi. Se tekee koodistasi helpommin ymmärrettävää ja ylläpidettävää.

```css
/* Block: Itsenäinen komponentti */
.tuotekortti {
    padding: 20px;
    background: white;
}

/* Element: Komponentin osa */
.tuotekortti__otsikko {
    font-size: 24px;
}

/* Modifier: Komponentin variaatio */
.tuotekortti--tarjous {
    border: 2px solid gold;
}
```

## CSS-esikäsittelijät (Sass)

Sass on kuin monitoimikone keittiössäsi - se tekee CSS:n kirjoittamisesta helpompaa ja tehokkaampaa. Se antaa sinun käyttää muuttujia, funktioita ja muita hyödyllisiä ominaisuuksia.

```scss
// Muuttujat
$primary-color: #3498db;
$spacing: 20px;

// Mixin - uudelleenkäytettävä tyylipaketti
@mixin flex-center {
    display: flex;
    justify-content: center;
    align-items: center;
}

.nappi {
    background: $primary-color;
    padding: $spacing;
    
    // Sisäkkäiset säännöt
    &:hover {
        background: darken($primary-color, 10%);
    }
}

.container {
    @include flex-center;
}
```

## Selaintuki ja prefix-määrittelyt

Eri selaimet ovat kuin eri kielet - joskus tarvitsemme käännöksiä, jotta kaikki ymmärtävät koodiamme. Näitä käännöksiä kutsutaan prefix-määrittelyiksi.

```css
.laatikko {
    /* Modernit selaimet */
    transform: rotate(45deg);
    
    /* Vanhemmat selaimet */
    -webkit-transform: rotate(45deg); /* Safari, Chrome */
    -moz-transform: rotate(45deg);    /* Firefox */
    -ms-transform: rotate(45deg);     /* Internet Explorer */
}
```

## Koodin optimointi ja minimointi

Ajattele tätä kuin tavaroiden pakkaamista matkalaukkuun - haluamme kaiken mahtumaan mahdollisimman pieneen tilaan menettämättä mitään tärkeää.

```css
/* Ennen optimointia */
.nappi {
    background-color: #ffffff;
    margin-top: 10px;
    margin-right: 20px;
    margin-bottom: 10px;
    margin-left: 20px;
}

/* Optimoinnin jälkeen */
.nappi {
    background: #fff; /* Lyhyempi värikoodi */
    margin: 10px 20px; /* Yhdistetty marginaali */
}
```

## Kriittisen CSS:n hallinta

Kriittinen CSS on kuin ravintolan alkuruoka - se on ensimmäinen asia, jonka käyttäjä näkee ja sen pitää olla nopeasti saatavilla. Se sisältää vain välttämättömimmät tyylit sivun ensimmäiseen näkymään.

```html
<head>
    <!-- Kriittiset tyylit suoraan HTML:ssä -->
    <style>
        /* Vain tärkeimmät tyylit */
        .header {
            background: #fff;
            padding: 20px;
        }
        .nav-main {
            display: flex;
        }
    </style>
    
    <!-- Muut tyylit ladataan myöhemmin -->
    <link rel="stylesheet" href="styles.css" media="print" onload="this.media='all'">
</head>
```

## Suorituskyvyn mittaaminen ja työkalut

Google Lighthouse on sisäänrakennettu Chrome-selaimen DevTools-työkaluihin ja se tarjoaa kattavan analyysin sivustosi suorituskyvystä. Se mittaa erityisesti:

- **First Contentful Paint (FCP)** - Aika, joka kuluu ensimmäisen sisällön näyttämiseen
- **Largest Contentful Paint (LCP)** - Sivun suurimman elementin latausaika
- **Time to Interactive (TTI)** - Milloin sivu on täysin interaktiivinen
- **Cumulative Layout Shift (CLS)** - Sivun elementtien liikkuminen latauksen aikana

PageSpeed Insights tarjoaa samankaltaisen analyysin, mutta testaa sivustoasi myös mobiililaitteilla ja eri verkkoyhteyksillä.

## Saavutettavuuden työkalut

### WAVE (Web Accessibility Evaluation Tool)

WAVE-työkalu ([wave.webaim.org](https://wave.webaim.org)) auttaa tunnistamaan saavutettavuusongelmia:

- Kontrastisuhteiden tarkistus
- Alt-tekstien puuttuminen
- Otsikkohierarkian ongelmat
- Lomakkeiden saavutettavuus

## Värien hallinta

### Väripalettityökalut

- **ColorSpace**: Tekoälyä hyödyntävä työkalu, joka generoi väripaletteja yhden värin pohjalta
- **Coolors.co**: Generoi harmonisia väripaletteja ja tarkista niiden saavutettavuus
- **Adobe Color**: Ammattimainen työkalu väriharmonioiden luomiseen
- **Paletton**: Luo monipuolisia väripaletteja eri väriteorioiden pohjalta



Muista, että sivuston optimointi on jatkuva prosessi, ei kertaluontoinen tehtävä. Aivan kuten ravintolan täytyy jatkuvasti kehittää reseptejään ja palveluaan, nettisivujen suorituskykyä tulee seurata ja parantaa säännöllisesti. Aloita pienistä parannuksista ja rakenna niistä vähitellen tehokas kokonaisuus.
