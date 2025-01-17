# Flexbox - Joustava sivun asettelu

Flexbox on moderni tapa asetella elementtejä verkkosivulla joustavasti ja responsiivisesti. Ajattele sitä kuin joustavaa säilytyslaatikkoa, jossa tavarat järjestyvät automaattisesti parhaalla mahdollisella tavalla.

## Flex Container ja Flex Items

Flex-asettelussa on aina säiliö (container) ja sen sisällä olevia elementtejä (items):

```css
/* Flex container - säiliö */
.container {
    display: flex;          /* Muuttaa elementin flex-säiliöksi */
    
    /* Vaihtoehtoinen tapa */
    display: inline-flex;   /* Flex-säiliö, joka ei vie koko leveyttä */
}

/* Flex items - säiliön sisällä olevat elementit */
.item {
    /* Kaikista container-elementin lapsista tulee automaattisesti flex-itemejä */
    margin: 10px;          /* Itemien väliin tilaa */
}
```

## Pääakseli ja poikkiakseli

Flex-asettelussa on kaksi akselia, joiden mukaan elementit järjestyvät:

```css
.container {
    /* Määrittää pääakselin suunnan */
    flex-direction: row;            /* Vaakasuunta (oletus) */
    flex-direction: row-reverse;    /* Vaakasuunta oikealta vasemmalle */
    flex-direction: column;         /* Pystysuunta */
    flex-direction: column-reverse; /* Pystysuunta alhaalta ylös */
}
```

## Järjestys ja suunta

Elementtien järjestystä ja suuntaa voi hallita monipuolisesti:

```css
.container {
    /* Elementtien järjestys pääakselilla */
    justify-content: flex-start;    /* Alusta (oletus) */
    justify-content: flex-end;      /* Lopusta */
    justify-content: center;        /* Keskeltä */
    justify-content: space-between; /* Tasaisin välein */
    justify-content: space-around;  /* Tasaiset marginaalit */
    
    /* Elementtien asettelu poikkiakselilla */
    align-items: stretch;           /* Venyttää koko korkeudelle (oletus) */
    align-items: flex-start;        /* Ylös/vasemmalle */
    align-items: flex-end;          /* Alas/oikealle */
    align-items: center;            /* Keskelle */
    align-items: baseline;          /* Tekstin peruslinjan mukaan */
}

/* Yksittäisen itemin asettelu poikkiakselilla */
.item {
    align-self: center;             /* Ylittää container-asetuksen */
}
```

## Tasaus ja välistys

Elementtien välisiä suhteita voi säätää monin tavoin:

```css
.container {
    /* Välit elementtien välillä */
    gap: 20px;                     /* Tasainen väli kaikkiin suuntiin */
    gap: 20px 10px;                /* Pysty- ja vaakavälit erikseen */
    
    /* Monirivisen flex-säiliön rivien tasaus */
    align-content: flex-start;     /* Rivit alkavat ylhäältä */
    align-content: center;         /* Rivit keskitetään */
    align-content: space-between;  /* Rivit tasaisin välein */
}
```

## Flex-grow, shrink ja basis

Nämä määrittävät, miten elementit kasvavat ja kutistuvat:

```css
.item {
    /* Kasvaminen suhteessa muihin */
    flex-grow: 1;                  /* Kasvaa täyttämään tilan */
    flex-grow: 2;                  /* Kasvaa kaksi kertaa enemmän */
    
    /* Kutistuminen tarvittaessa */
    flex-shrink: 1;                /* Sallii kutistumisen (oletus) */
    flex-shrink: 0;                /* Ei kutistu */
    
    /* Lähtökoko */
    flex-basis: 200px;             /* Elementin peruskoko */
    flex-basis: auto;              /* Koko sisällön mukaan */
    
    /* Lyhyt muoto kaikille kolmelle */
    flex: 1 1 auto;                /* grow shrink basis */
}
```

## Flex-wrap

Määrittää, miten elementit käyttäytyvät, kun tila loppuu:

```css
.container {
    /* Rivien hallinta */
    flex-wrap: nowrap;             /* Kaikki yhdelle riville (oletus) */
    flex-wrap: wrap;               /* Siirtyy uudelle riville */
    flex-wrap: wrap-reverse;       /* Siirtyy uudelle riville ylöspäin */
    
    /* Yhdistelmä suunnalle ja wrapille */
    flex-flow: row wrap;           /* direction ja wrap yhdessä */
}
```

## Muista nämä Flexboxin tärkeimmät periaatteet:

- **Container** hallitsee kokonaisuutta, **itemit** mukautuvat
- **Pääakseli** määrää perussuunnan (`row` tai `column`)
- `justify-content` vaikuttaa pääakseliin, `align-items` poikkiakseliin
- `flex-grow`, `shrink` ja `basis` hallitsevat itemien kokoa
- `flex-wrap` määrää, miten elementit reagoivat tilan loppumiseen
