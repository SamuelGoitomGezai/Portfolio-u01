[Min publicerade portfoliosida](https://samuelgoitomgezai.github.io/Portfolio-u01/)

## Reflektion

### Från skiss till kod

I början kände jag mig osäker på CSS, framför allt hur text och bilder skulle placeras. Det var mycket att hålla reda på samtidigt. Sidan skulle både likna skissen och fungera när fönstret blev mindre, så det räckte inte att bara få den att se bra ut på en stor skärm.

Jag utgick från skissens layout, färger och typsnitt, men använde mitt namn, min bild och mina uppgifter. Porträttet är till exempel runt med en färgad kant. I `base.css` använder `.hero-photo` bland annat `object-fit: cover`. Det gör att bilden fyller sin yta utan att bli utdragen.

Ett problem var att mappen med teknikikoner först hamnade bredvid `images`. Jag flyttade in den så att sökvägen `images/icons` stämde med HTML-filen. När jag granskade innehållet upptäckte jag också att Fisksätra Fryshuset saknades under fritidsledare på About-sidan. Jag rättade det och ändrade presentationen till ”22 år gammal”.

### Semantik

Jag använde `header` för sidhuvudet, `nav` för navigationen, `main` för huvudinnehållet och `footer` för sidfoten. Dessa element beskriver vilken funktion delarna har. En vanlig `div` hade kunnat få samma utseende med CSS, men den berättar inte att innehållet exempelvis är en meny.

I `about.html` ligger arbetslivserfarenhet och utbildning i varsin `section` med en egen rubrik. De handlar om olika ämnen och passar därför som separata avsnitt. I `projects.html` använder jag `article` för varje projektkort, eftersom varje kort är en egen presentation. Sidans huvudrubrik är `h1` och projektkortens rubriker är `h2`.

Jag använder också `div` där det främst behövs en behållare för layouten. Ett exempel är `.hero-text` i `index.html`, som håller ihop rubriken och presentationstexten. Där behövs inget extra innehållsavsnitt med en egen rubrik.

### Layout och responsivitet

På startsidan använder `.hero` i `base.css` Flexbox. Texten och bilden ligger under varandra i den smala vyn och bredvid varandra från 1024 pixlar. Flexbox passar eftersom det handlar om två delar som ska ordnas i en rad eller kolumn.

Till projektkorten använder jag Grid i `.projects-grid` i `projects.css`. Där behöver flera kort placeras i jämna rader och kolumner. Grundläget har en kolumn, från 800 pixlar blir det två och från 1200 pixlar tre. Jag valde dessa brytpunkter för att kortens text skulle få tillräckligt med plats innan fler kolumner lades till.

Menyn byter också layout vid 1024 pixlar. Under den bredden visas en menyknapp, eftersom logotypen, länkarna och profilikonerna annars tar för mycket plats på samma rad. Mobilmenyn använder `details` och `summary`, vilket gör att den kan öppnas och stängas utan JavaScript.

Gemensamma färger ligger som variabler i `base.css`, till exempel `--heading-color`. Då kan samma färg återanvändas och ändras på ett ställe. Jag använder även `box-sizing: border-box`, så att padding och kantlinjer räknas in i elementets angivna bredd.

### Tillgänglighet och tester

Jag testade sidan i Chrome, Safari och Firefox. I Firefox gick jag igenom alla fem sidor och kontrollerade att teknikikonerna, de sex projektbilderna och sidfötterna syntes.

Jag gjorde också fönstret smalare för att kontrollera layouten. På Contact-sidan bröts mejladressen på två rader och höll sig innanför sidan. I `contact.css` finns `overflow-wrap: anywhere`, som gör att en lång adress kan brytas i stället för att skapa innehåll utanför sidans bredd.

För att testa tangentbordsnavigation använde jag Tab och Retur. I Firefox kunde jag öppna mobilmenyn och gå till Contact utan mus. I Safari behövde jag hålla nere Option tillsammans med Tab för att nå länkarna. Fokusramen visade vilket alternativ som var markerat. Den styrs med `:focus-visible` i `layout.css`.

Länken ”Hoppa till innehållet” gör det möjligt att gå förbi menyn med tangentbordet. Porträttet har en beskrivande alt-text, medan dekorativa bilder har tom alt-text. Profillänkarna har också beskrivande namn så att deras funktion inte bara framgår av ikonerna.

En tidigare version av de fem HTML-sidorna kontrollerades med W3C utan HTML-fel, men med varningar om `role="list"`. About-texten ändrades efter den kontrollen. En fullständig tillgänglighetsgranskning återstår. Mina visuella kontroller och tangentbordstester räcker inte för att säga att allt fungerar för alla användare.

### Styrkor och brister

Jag tycker att resultatet blev ganska bra. Menyn, färgerna och typsnitten håller ihop sidorna. Bilderna laddades och innehållet fick plats i de smala vyer jag kontrollerade.

En brist är att Projects fortfarande innehåller exempelkort, utan riktiga demos och kodlänkar. Därför står det tydligt att egna projekt kommer senare.

Med mer tid skulle jag se över den upprepade menykoden. Samma länkar finns i både mobil- och desktopmenyn på varje sida. Det innebär att en ändring behöver göras på flera ställen, vilket ökar risken att någon länk missas.

### AI-verktyg

Jag har fått hjälp av AI med grammatiken och med att formulera och strukturera reflektionen så att svaren följer frågornas ordning. Jag har också fått hjälp att tolka resultaten från [W3C:s HTML-validator](https://validator.w3.org/) vid kontroll och felsökning av HTML-koden.