# CSS Box Model ja Layout - Elementtien tilankäyttö ja sijoittelu

CSS:ssä jokainen elementti on kuin laatikko verkkosivun tilassa. Ajattele sitä kuin huonekalujen järjestämistä huoneessa - jokaisella on oma tilansa ja suhteensa muihin elementteihin.

## Box Model - Laatikkomalli

Box Model määrittelee, miten elementti käyttää tilaa sivulla:

```css
.elementti {
    /* Sisällön koko */
    width: 300px;
    height: 200px;

    /* Sisäinen täyte */
    padding: 20px;                /* Kaikki sivut */
    padding: 10px 20px;           /* Ylös/alas, vasen/oikea */
    padding: 10px 20px 15px 25px; /* Ylä, oikea, ala, vasen */

    /* Reunus */
    border: 2px solid black;      /* Paksuus, tyyli, väri */
    border-radius: 5px;           /* Pyöristetyt kulmat */

    /* Ulkoinen marginaali */
    margin: 15px;                 /* Kaikki sivut */
    margin: 0 auto;               /* Keskitys vaakasuunnassa */
}
```

## Box-sizing - Koon laskeminen

Box-sizing määrittää, miten elementin kokonaiskoko lasketaan:

```css
/* Oletustapa: width/height koskee vain sisältöä */
.oletuslaatikko {
    box-sizing: content-box;
    width: 100px;     /* Kokonaisleveys = 100px + padding + border */
}

/* Järkevämpi tapa: width/height sisältää paddingin ja borderin */
* {
    box-sizing: border-box;    /* Asetetaan yleensä kaikille elementeille */
}
```

## Display - Elementtien näyttötapa

Display määrittää, miten elementti käyttäytyy suhteessa muihin:

```css
.elementti {
    /* Perusnäyttötavat */
    display: block;          /* Vie koko rivin leveyden */
    display: inline;         /* Vain tarvittavan tilan */
    display: inline-block;   /* Yhdistelmä molempia */
    display: none;           /* Piilottaa elementin */

    /* Flex-laatikko (moderni tapa) */
    display: flex;           /* Joustava laatikkomalli */
    flex-direction: row;     /* Suunta: vaakataso */
    justify-content: center; /* Keskitys vaakasuunnassa */
    align-items: center;     /* Keskitys pystysuunnassa */
}
```

## Position - Elementin sijoittaminen

Position määrittää, miten elementti sijoitetaan suhteessa muihin:

```css
.elementti {
    /* Perussijoitustavat */
    position: static;        /* Oletusarvo, normaali sijainti */
    
    position: relative;      /* Suhteessa normaaliin sijaintiin */
    top: 10px;
    left: 20px;
    
    position: absolute;      /* Suhteessa lähimpään position-vanhempaan */
    top: 0;
    right: 0;
    
    position: fixed;         /* Pysyy paikallaan vieritettäessä */
    bottom: 20px;
    right: 20px;
    
    position: sticky;        /* Pysyy näkyvissä vieritettäessä */
    top: 0;
}
```

## Float ja Clear - Kelluvat elementit

Float sallii elementtien "kellumisen" sivulla:

```css
.kelluva {
    float: left;            /* Kelluu vasemmalle */
    float: right;           /* Kelluu oikealle */
}

.seuraava {
    clear: both;            /* Estää kellumisen molemmilta puolilta */
    clear: left;            /* Estää vasemmalle kellumisen */
    clear: right;           /* Estää oikealle kellumisen */
}
```

## Z-index - Elementtien päällekkäisyys

Z-index määrittää elementtien piirtojärjestyksen:

```css
.alapuolella {
    position: relative;     /* Z-index toimii vain sijoitetuilla elementeillä */
    z-index: 1;            /* Pienempi numero = alempana */
}

.paalla {
    position: relative;
    z-index: 2;            /* Suurempi numero = päällä */
}
```

## Tärkeät muistisäännöt:

- **Box Model** on perusta kaikelle layoutille
- `box-sizing: border-box` tekee koon hallinnasta helpompaa
- **Flex** on moderni ja suositeltu tapa asetteluun
- **Position**-ominaisuutta käytetään erityistapauksiin
- `Z-index` toimii vain elementeille, joilla on `position`-arvo
- **Float** on vanhentuva tekniikka - suosi Flexiä
