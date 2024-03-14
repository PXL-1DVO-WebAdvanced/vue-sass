# Vue.js - integratie Sass

We gaan het resultaat van [scss-opdracht2](https://github.com/PXL-1DVO-WebAdvanced/scss-opdracht2/blob/oplossing/index.html) integreren in een Vue applicatie. 

## Setup
- Maak een nieuw Vue project aan (bij het aanmaken moet je geen enkele van de opties gebruiken)
- Verwijder de bestanden en mappen van het nieuwe project die je niet nodig hebt
    - Maak de assets-folder leeg 
    - Verwijder de components-folder
    - Verwijder de views-folder
    - Initialiseer het App.vue bestand

## HTML
- Kopieer de inhoud van de body-tag uit het index.html uit scss-opdracht2 naar de template-tag van Vue.app

## Opmaak
Omdat Vite gebruikt wordt voor de build van onze Vue applicatie kan de Sass code op een efficiëntere manier gebruikt worden. 
- Installeer het Sass package:

        npm install -D sass

    -D staat voor *dev*, We gaan het builden namelijk enkel gebruiken tijdens development. [(Meer info)](https://vitejs.dev/guide/features.html#css-pre-processors)

- Vite zal het builden (compileren) van de Sass code afhandelen. Hiervoor dien je het volgende te doen:
    - Kopieer de scss-folder van scss-opdracht2 naar de root-folder van je project
        - _footer.scss
        - _global.scss
        - _nav.scss
        - _section.scss
        - main.scss
    - **Link het pad naar het main.scss bestand bovenaan in *main.js* als volgt:**

            import '../scss/main.scss'
            ...

- Start je applicatie en bekijk het resultaat!

        npm run dev

## Afbeeldingen
- Voeg de afbeelding favouritetools.jpg toe aan de assets-folder
- Toon deze afbeelding als laatste element van de banner

Om de afbeelding te tonen ga je het pad naar de afbeelding moeten wijzigen. Doordat Vite wordt gebruikt is er een configuratiebestand aanwezig: vite.config.js. Hierin zal je een alias '@' zien die leidt naar de src-folder van het project. Dit zal ervoor zorgen dat het pad dynamisch wijzigt afhankelijk van de locatie (bv lokaal bij developer of op een server in productie). Je kan een relatief pad dus als volgt opbouwen:

        <img src="@/assets/images/random.png" alt="random image" />

## Variabelen
- Voorzie voor alle HTML-elementen een variabele in de script-tag van het App.vue-bestand
    - navWebEss
    - navWebAdv
    - navWebExp
    - bannerTitle
    - bannerText
    - footerTitle
    - footerText
- Koppel deze variabelen aan de HTML-template door gebruik te maken van databinding en interpolatie.
- Gebruik nu in plaats van 7 aparte variabelen:
    - Een array *navItems* die 3 elementen bevat
        Tip: gebruik v-for in het li-element van de template
    - Een object *banner* met 2 eigenschappen: title + text
    - Een object *footer* met 2 eigenschappen: title + text

            navItems: [...],
            banner: {
                title: '...',
                text: '...'
            },
            footer: {
                title: '...',
                text: '...'
            }

