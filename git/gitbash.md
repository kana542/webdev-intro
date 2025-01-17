# Git Bash

## Sisällysluettelo

1. [Git Bash kehittäjän työympäristönä](#git-bash-kehittäjän-työympäristönä)
2. [Integraatio paketinhallintajärjestelmien kanssa](#integraatio-paketinhallintajärjestelmien-kanssa)
3. [Tiimityöskentelyn tuki](#tiimityöskentelyn-tuki)
4. [Unix-yhteensopivuus Windowsissa](#unix-yhteensopivuus-windowsissa)
5. [Tekniset ohjeet ja komennot](#tekniset-ohjeet-ja-komennot)
    - [Git Bashin käynnistys ja navigointi](#git-bashin-käynnistys-ja-navigointi)
    - [Navigointikomennot](#navigointikomennot)
    - [Tiedostojen käsittely](#tiedostojen-käsittely)
6. [Git-toiminnot](#git-toiminnot)
    - [Perustoiminnot](#perustoiminnot)
    - [Edistyneet toiminnot](#edistyneet-toiminnot)
7. [Node.js ja NPM](#nodejs-ja-npm)
    - [Projektin aloitus](#projektin-aloitus)
    - [Pakettien hallinta](#pakettien-hallinta)
    - [NPM skriptit](#npm-skriptit)
8. [Projektin rakenne](#projektin-rakenne)
    - [Perusrakenne](#perusrakenne)
    - [Tärkeät tiedostot ja niiden luonti](#tärkeät-tiedostot-ja-niiden-luonti)
9. [Virhetilanteet ja ratkaisut](#virhetilanteet-ja-ratkaisut)
10. [Parhaat käytännöt](#parhaat-käytännöt)
11. [Käytännön työnkulku esimerkki](#käytännön-työnkulku-esimerkki)
12. [Lisäresurssit](#lisäresurssit)

---

## Git Bash kehittäjän työympäristönä

Git Bash toimii kehittäjän komentokeskuksena, joka yhdistää eri kehitystyökalut yhteen paikkaan. Ajattele sitä ikään kuin työpöytänä, joka yhdistää Git-versionhallinnan ja Unix-tyylisen komentorivikäyttöliittymän Windows-ympäristössä. Se mahdollistaa sekä Git-komentojen että Unix-tyylisten komentojen käytön.

## Integraatio paketinhallintajärjestelmien kanssa

Kun käytät npm: ä (Node Package Manager) Git Bashissa, se integroituu saumattomasti muiden työkalujen kanssa. Voit esimerkiksi hallinnoida npm-paketteja, ajaa Git-komentoja ja käsitellä tiedostoja kaikki samasta paikasta. Tämä on kuin rakentaisit taloa: Git Bash on työmaasi, Git on sinun rakennussuunnitelmasi, ja npm tuo rakennusmateriaalit (eli paketit ja kirjastot) käyttöösi.

## Tiimityöskentelyn tuki

Git Bash yhdistää kaikki työkalut yhtenäiseksi työnkuluksi. Voit helposti siirtyä koodin kirjoittamisesta pakettien hallintaan, versioiden päivittämiseen ja koodin jakamiseen tiimisi kanssa. Tämä on erityisen hyödyllistä isoissa projekteissa, joissa on monia riippuvuuksia ja useita kehittäjiä.

## Unix-yhteensopivuus Windowsissa

Git Bash tuo Unix-tyylisen ympäristön Windows-koneellesi, mikä on erityisen hyödyllistä, koska monet kehitystyökalut on suunniteltu Unix-ympäristöä ajatellen. Tämä yhtenäistää kehityskokemuksen eri käyttöjärjestelmien välillä.

---

## Tekniset ohjeet ja komennot

### Git Bashin käynnistys ja navigointi

Git Bash avautuu oletuksena C:-aseman juureen (esim. `C:\Users\KäyttäjäNimi`). Kansiosta toiseen siirtymiseen on kaksi tapaa:

1. **Navigointi komentoriviltä**  
   Sinun täytyy navigoida kansio kerrallaan oikeaan sijaintiin. Esimerkki: Jos luot kansion "developer" oletuskansioon "Tiedostot" (`C:\Users\KäyttäjäNimi\Documents`), kirjoita:
   ```bash
   cd Documents
   cd developer
   ```
   tai kaikki kerralla:
   ```bash
   cd Documents/developer
   ```

3. **Git Bashin pikakäynnistys oikeassa kansiossa**

![screenshot](https://github.com/user-attachments/assets/bc450175-e3aa-4192-b3f4-4e63f7bbbe6e)


   - Navigoi haluamaasi kansioon  
   - Klikkaa kansiota hiiren oikealla painikkeella  
   - Valitse valikosta "Open Git Bash here"  
   - Git Bash avautuu suoraan valitussa kansiossa  

### Navigointikomennot

```bash
pwd                     # Näytä nykyinen sijainti
ls                      # Listaa tiedostot
ls -la                  # Listaa kaikki tiedostot yksityiskohtaisesti
cd kansio               # Siirry kansioon
cd ..                   # Siirry ylos
cd ~                    # Siirry kotikansioon
```

### Tiedostojen käsittely

```bash
mkdir kansio            # Luo kansio
touch tiedosto.txt      # Luo tiedosto
rm tiedosto.txt         # Poista tiedosto
rm -r kansio            # Poista kansio
cp tiedosto1 tiedosto2  # Kopioi
touch tiedosto.txt      # Uudelleennimeä
```

---

## Git-toiminnot

### Perustoiminnot

```bash
git init                # Alusta repositorio
git clone url           # Kloonaa repositorio
git status              # tarkista oletukset/ohjeille tekstille
git add tiedosto        # Lisää tiedosto
git add .               # Lisää kaikki
git commit -m "viesti"  # Tee commit
git push                # Lähetä muutokset
git pull                # Hae muutokset
```

### Edistyneet toiminnot

```bash
git branch              # Näytä haarat
git checkout -b haara   # Luo ja vaihda haaraan
git merge haara         # Yhdistä haarat
git stash               # Tallenna väliaikaisesti
git stash pop           # Palauta tallennetut
```

## Node.js ja NPM

### Projektin aloitus

```bash
node -v                 # Tarkista Node.js versio
npm -v                  # Tarkista NPM versio
npm init                # Alusta projekti
npm init -y             # Alusta oletusasetuksilla
```

### Pakettien hallinta

```bash
npm install paketti     # Asenna paketti
npm i paketti           # Lyhyt muoto
npm install -g paketti  # Globaali asennus
npm install --save-dev paketti # Kehitysriippuvuus
```

### NPM skriptit

```json
{
  "scripts": {
    "start": "node index.js",
    "dev": "nodemon index.js",
    "test": "jest",
    "build": "webpack"
  }
}
```

## Projektin rakenne

### Perusrakenne

```plaintext
projekti/
├── src/              # Lähdekoodi
│   ├── index.js     # Pääsisäänkäynti
│   ├── routes/      # Reititys
│   ├── controllers/ # Logiikka
│   └── models/      # Tietomallit
├── public/          # Staattiset tiedostot
├── tests/           # Testit
└── dist/            # Käännetty koodi
```

### Tärkeät tiedostot ja niiden luonti

#### Automaattisesti luotavat tiedostot/kansiot

**`package.json`**
- Luodaan `npm init` tai `npm init -y` komennolla
- Sisältää projektin määrittelyt, riippuvuudet ja skriptit

**`node_modules/`**
- Luodaan automaattisesti, kun asennat paketteja (`npm install`)
- Sisältää kaikki asennetut paketit
- Ei pidä koskaan lisätä versionhallintaan

**`package-lock.json`**
- Luodaan automaattisesti pakettien asennuksen yhteydessä
- Lukitsee pakettien versiot
- Tärkeä sisällyttää versionhallintaan

#### Itse luotavat tärkeät tiedostot

**`.env`**
- Pitää luoda itse
- Sisältää ympäristömuuttujat
- Esimerkki sisällöstä:

```env
PORT=3000
DATABASE_URL=mongodb://localhost/mydb
API_KEY=your_secret_key
```

**`.gitignore`**
- Pitää luoda itse
- Määrittelee mitkä tiedostot/kansiot git jättää huomiotta
- Tärkeä perusrakenne:

```gitignore
node_modules/
.env
.DS_Store
dist/
build/
```

**`README.md`**
- Pitää luoda itse
- Projektin dokumentaatio
- Tärkeä lisätä heti projektin alussa

**`src/`**
- Pitää luoda itse
- Sisältää projektin lähdekoodin
- Yleinen käytäntö modernissa Node.js-kehityksessä

### Lisäkonfiguraatiot (vapaaehtoisia)

**`.eslintrc.js/.eslintrc.json`**
- Luodaan `eslint --init` komennolla
- Koodin laadun tarkistus

**`.prettierrc`**
- Pitää luoda itse
- Koodin muotoilusäännöt

```json
{
  "singleQuote": true,
  "trailingComma": "all",
  "printWidth": 80
}
```

## Virhetilanteet ja ratkaisut

Git Bashin käytössä voi ilmetä erilaisia virhetilanteita. Virheet ovat yleisiä ja kuuluvat ohjelmistokehityksen arkeen - niitä ei kannata säikähtää. Useimpiin virheisiin löytyy ratkaisu verkosta hakemalla virheilmoitusta.

## Parhaat käytännöt

### Versiointi

- Käytä semanttista versiointia
- Päivitä `package.json` säännöllisesti

### Turvallisuus

- Älä tallenna salaisuuksia versionhallintaan
- Käytä `.env` tiedostoja
- Tarkista riippuvuudet: `npm audit`

### Dokumentointi

- Pidä `README.md` ajan tasalla
- Dokumentoi API-muutokset
- Kommentoi koodi selkeästi

## Käytännön työnkulku esimerkki

### Uuden projektin aloitus

```bash
mkdir uusi-projekti
cd uusi-projekti
git init
npm init -y
```

### Pakettien asennus

```bash
npm install express dotenv
npm install --save-dev nodemon jest
```

### Projektin rakenteen luonti

```bash
mkdir src
touch src/index.js
touch .env
touch .gitignore
```

### Versionhallinta

```bash
git add .
git commit -m "Projektin alustus"
git push
```

## Lisäresurssit

- Git-Book: https://git-scm.com/doc](https://git-scm.com/book/en/v2
