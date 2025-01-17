# CSS Grid - Ruudukkomainen sivun asettelu

CSS Grid on tehokas tapa luoda kaksiulotteisia asetteluja verkkosivuille. Ajattele sitä kuin taulukkoa tai ruutupaperia, johon voit järjestellä sisältöä sekä vaaka- että pystysuunnassa samanaikaisesti.

## Grid Container ja Grid Items

Grid-asettelu alkaa säiliön määrittelystä:

```css
/* Grid container - pääsäiliö */
.container {
    display: grid;                    /* Muuttaa elementin grid-säiliöksi */
    /* tai */
    display: inline-grid;             /* Grid-säiliö, joka ei vie koko leveyttä */
}

/* Grid items - säiliön sisällä olevat elementit */
.item {
    /* Kaikista container-elementin lapsista tulee automaattisesti grid-itemejä */
    border: 1px solid black;          /* Visualisoi ruudut */
}
```

## Rivit ja sarakkeet

Ruudukon perusrakenteen määrittely:

```css
.container {
    /* Määrittelee sarakkeiden määrän ja koon */
    grid-template-columns: 100px 200px 100px;   /* 3 saraketta kiinteillä leveyksillä */
    grid-template-columns: 1fr 2fr 1fr;         /* Suhteelliset leveydet */
    grid-template-columns: repeat(3, 1fr);      /* 3 yhtä leveää saraketta */
    
    /* Määrittelee rivien määrän ja koon */
    grid-template-rows: 100px auto 200px;       /* 3 riviä eri korkeuksilla */
    grid-template-rows: repeat(3, minmax(100px, auto)); /* Joustava minimikorkeus */
}
```

## Grid-template-areas

Alueiden nimeäminen ja visuaalinen sijoittelu:

```css
.container {
    /* Määritellään ruudukon alueet */
    grid-template-areas: 
        "header header header"
        "sidebar content content"
        "footer footer footer";
}

/* Elementtien sijoittaminen alueille */
.header {
    grid-area: header;    /* Sijoittaa elementin header-alueelle */
}
.sidebar {
    grid-area: sidebar;   /* Sijoittaa elementin sidebar-alueelle */
}
.content {
    grid-area: content;   /* Sijoittaa elementin content-alueelle */
}
.footer {
    grid-area: footer;    /* Sijoittaa elementin footer-alueelle */
}
```

## Gap-ominaisuudet

Ruudukon välien hallinta:

```css
.container {
    /* Välit rivien ja sarakkeiden välillä */
    gap: 20px;                     /* Sama väli kaikkialla */
    gap: 20px 10px;                /* Riviväli ja sarakeväli erikseen */
    
    /* Voidaan määritellä myös erikseen */
    row-gap: 20px;                 /* Vain rivien välit */
    column-gap: 10px;              /* Vain sarakkeiden välit */
}
```

## Tasaus ja sijoittelu

Elementtien tarkka sijoittelu ruudukossa:

```css
.item {
    /* Elementin sijainti ruudukossa */
    grid-column: 1 / 3;            /* Leveys sarakkeesta 1 sarakkeeseen 3 */
    grid-row: 2 / 4;               /* Korkeus riviltä 2 riville 4 */
    
    /* Lyhyempi tapa määritellä sijainti */
    grid-area: 2 / 1 / 4 / 3;      /* rivi-alku / sarake-alku / rivi-loppu / sarake-loppu */
    
    /* Elementin tasaus ruudun sisällä */
    justify-self: center;          /* Vaakasuuntainen keskitys */
    align-self: center;            /* Pystysuuntainen keskitys */
}
```

## Automaattinen sijoittelu

Grid osaa sijoitella elementtejä myös automaattisesti:

```css
.container {
    /* Automaattinen rivien luonti */
    grid-auto-rows: 100px;         /* Uusien rivien korkeus */
    
    /* Automaattinen sarakkeiden luonti */
    grid-auto-columns: 1fr;        /* Uusien sarakkeiden leveys */
    
    /* Automaattisen sijoittelun suunta */
    grid-auto-flow: row;           /* Vaakasuuntainen (oletus) */
    grid-auto-flow: column;        /* Pystysuuntainen */
    grid-auto-flow: dense;         /* Täyttää tyhjät kohdat */
}
```

## Tärkeimmät periaatteet CSS Gridin käytössä:

- **Grid** on kaksiulotteinen järjestelmä, toisin kuin Flexbox
- `Template-areas` tekee layoutin suunnittelusta visuaalista
- `fr`-yksikkö auttaa luomaan joustavia ruudukoita
- `Gap`-ominaisuudet tekevät väleistä tasaisia
- Automaattinen sijoittelu helpottaa dynaamisen sisällön kanssa
