#Predstavenie Bootstrap 4 Alpha
Bootstrap je dnes veľmi známy a populárny front-endový framework, ktorý [19. augusta](http://blog.getbootstrap.com/2015/08/19/bootstrap-4-alpha/) oslávil svoje štvrté narodeniny.

Ako darček pre nás jeho tvorcovia, [Mark Otto](https://twitter.com/mdo) a [Jacob Thornton](https://twitter.com/fat), pripravili vydanie [alpha verzie úplne nového Bootstrap 4](http://blog.getbootstrap.com/2015/08/19/bootstrap-4-alpha/).

##Čo je to front-end framework
Na začiatok si v krátkosti povieme, čo to vlastne front-end framework je.

Slovo framework môžeme poznať napríklad z PHP (Nette, Laravel, ...) a aj v tomto prípade sa jedná o sadu nástrojov, ktoré nám v tomto prípade uľahčujú tvorbu front-endov pre naše webové aplikácie.

Najčastejšie front-end framework pozostáva z HTML šablón a CSS súborov definujúcich typografiu, formulárové prvky, tlačítka, navigáciu a iné vizuálne prvky, ktoré môžeme veľmi ľahko zobrať z dokumentácie a použiť.

Ďaľším častým prvkom tvoriacim front-end framework sú JavaScript pluginy určené na zvýšenie interaktivity alebo maskovanie chýb prehliadačov. Medzi interaktívne JS pluginy sa častokrát radí napríklad tzv. carousel, tooltipy, modálne okná alebo zjednodušenie práce s animáciami.

Častokrát sa pri lepších frameworkoch stretneme aj s ukážkami kompletných rozhraní.

Pre porovnanie množstva dostupných front-end frameworkov môžete navštíviť [CSS Frontend Frameworks](https://usablica.github.io/front-end-frameworks/compare.html).

##	Všeobecné novinky

Ako najväčšiu zmenu vo verzii 4 môžeme brať prechod od LESS k SASS. Takáto zmena podľa autorov vraj prinesie zrýchlenie v oblasti kompilovania.

Osobne touto zmenou nie som veľmi nadšený, nakoľko som priaznivcom LESS, avšak verím, že autori mali svoj dôvod na túto zmenu, a tak ako sa kedysi objavil SASS port, pribudne neskôr LESS port najnovšej verzie.

Ďaľšou významnou zmenou je odstránenie podpory pre IE8. Najnižšie podporovanou verziou Internet Explorer-u sa tak stáva deviatka, ktorá už pozná viac CSS3 a dovoľuje tak Bootstrap-u lepšie optimalizovať svoj kód.

Tento posun umožnil v novej verzii používať jednotky `rem` a `em`, čo výrazne zjednodušuje prácu s responzívnym textom, ale aj veľkosťami ostatných elementov.

##Grid
S prechodom na vyššie spomínané `rem` a `em` jednotky prišiel aj nový vylepšený grid.

Zápis kódu zostal zachovaný a tak klasický 12-stĺpcový grid budeme stále zapisovať takto:

	<div class="container">
   		<div class="row">
       	<div class="col-md-6 col-lg-8">
          	<!-- Blah 1 -->
       	</div>
       	<div class="col-md-6 col-lg-4">
          	<!-- Blah 2 -->
       	</div>
    	</div>
	</div>
	

Zmenu nájdeme v nastavení triedy `container`, ktorej maximálna šírka je teraz uvádzaná v jednotkách `rem`. Podobnú zmenu nájdeme aj pri triede `row`, ktorej ľavý a pravý margin sa zmenil na `-.9375rem` a stĺpce `col-` dostali padding o veľkosti `0.9375rem`.

Tieto zmeny znamenajú, že všetko je dynamické a relatívne podľa `HTML` tagu.

###Flex Box
V najnovšej verzii Bootstrap-u budeme môcť pomocou jednoduchého nastavenia používať Grid s Flex Box modelom. Konkrétne je potrebné zmeniť parameter `$enable-flex` v súbore [`_variables.scss`](https://github.com/twbs/bootstrap/blob/v4-dev/scss/_variables.scss#L46) a prekompilovať.

**Upozornenie: Flex Box nie je podporovaný v IE9!**

###Media Queries
Vylepšeniami si prešli aj Media Queries, ktoré namiesto `px` už používajú `em` jednotky.

	// Extra small devices (portrait phones, less than ???px)
	// No media query since this is the default in Bootstrap
	
	// Small devices (landscape phones, 34em and up)
	@media (min-width: 34em) { ... }
	
	// Medium devices (tablets, 48em and up)
	@media (min-width: 48em) { ... }
	
	// Large devices (desktops, 62em and up)
	@media (min-width: 62em) { ... }
	
	// Extra large devices (large desktops, 75em and up)
	@media (min-width: 75em) { ... }
	
Oproti Bootstrap 3 bol navyše pridaný aj ďaľší bod a to `48em` čo je približne `480px`. Pridaním tohto bodu máme lepšiu kontrolu nad našimi rozhraniami.

##Karty
[Karty (Cards)](http://v4-alpha.getbootstrap.com/components/card/) sú novým elementom, ktorý nahradí [wells](http://getbootstrap.com/components/#wells), [panels](http://getbootstrap.com/components/#panels) a [thumbnails](http://getbootstrap.com/components/#thumbnails) z Bootstrap 3. Je to viacmenej taká kombinácia týchto elementov v podobe flexibilných kontajnerov pre váš obsah s veľkými možnosťami.

Karty tak môžu obsahovať hlavičku, obrázky, pätičku, zoznamy a podobne.
Za zmienku stoja aj takzvané **Card Groups** a **Card Decks**.

<p data-height="355" data-theme-id="18427" data-slug-hash="xwxPjG" data-default-tab="result" data-user="mattonik" class='codepen'>See the Pen <a href='http://codepen.io/mattonik/pen/xwxPjG/'>Bootstrap 4 Cards Demo</a> by Martin Puškáč (<a href='http://codepen.io/mattonik'>@mattonik</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

##Nový reset súbor - Reboot.css
Doteraz Bootstrap používal ako reset súbor veľmi populárny [Normalize.css](https://necolas.github.io/normalize.css). Pre štvrtú verziu sa rozhodli vytvoriť nový [Reboot.css](https://github.com/twbs/bootstrap/blob/v4-dev/scss/_reboot.scss), ktorý kombinuje pôvodný Normalize.css s Boostratp-u vlastnými parametrami. Vďaka tomuto je možné Reboot.css používať aj samostatne.

##Zmeny v JavaScript-e
Ako nám [blog post](http://blog.getbootstrap.com/2015/08/19/bootstrap-4-alpha/) napovedá, zásadné zmeny sa udiali aj v JavaScript pluginoch.

Za najvýraznejšiu zmenu môžeme považovať prepísanie všetkých pluginov do ES6 kompilovaného pomocou knižnice [Babel](https://babeljs.io/).

Ďaľším vítaným zlepšením je vyriešenie problémov s UMD a AMD:

* [AMD with concatenated JS file](https://github.com/twbs/bootstrap/issues/13812)
* [UMD Tests](https://github.com/twbs/bootstrap/pull/13843).

Vďaka zrušeniu podpory pre IE8 s Bootstrap 4 už budeme môcť smelo používať jQuery 2.0!

##Záver
Zoznam zmien tými vyššie spomínanými samozrejme nekončí. V novej verzii sa budeme môcť tešiť na vylepšené umiestňovanie tooltip-ov vďaka knižnici [Tether.js](http://github.hubspot.com/tether/), zmenám v práci s typografiou vďaka prechodu na `rem`, či novým pomocným triedam pre prácu s `margin` a `padding`.

Pre niektorých možno smutnou správou bude zastavenie podpory [Glyphicons](http://getbootstrap.com/components/#glyphicons).

Zmeny v Bootstrap 4 by mali priniesť jednoduchšiu prácu hlavne s responzívnym dizajnom a kompletné prepísanie pri prechode na SASS vraj ušetril až 30% z výsledného bootstrap.css) oproti Bootstrap 3, čo je naozaj slušné. Viac si môžete prečítať [v diskusii s @mdo na Hacker News](https://news.ycombinator.com/item?id=10086797).

Bootstrap 4 zatiaľ nemá stanovený dátum vydania, no ak ho chcete využiť pre svoj nový projekt, môžete si stiahnuť kód z [Github-u](https://github.com/twbs/bootstrap/tree/v4-dev).

Pre tých, ktorým vyhovuje existujúca verzia, majú autori dobrú správu a to zachovanie podpory pre túto verziu s vydávaním záplat a udržiavaním dokumentácie.

Ak by toho bolo predsalen málo, autori sa pochválili aj spustením oficiálneho [Bootstrap Themes](http://themes.getbootstrap.com/) projektu, kde už dnes môžete nájsť niekoľko Bootstrap 3 tém na kúpu.

###Zopár odkazov na záver

* [Bootstrap 4 Alpha dokumentácia](http://v4-alpha.getbootstrap.com/)
* [Bootstrap 4 branch na Github-e](https://github.com/twbs/bootstrap/tree/v4-dev)
* [Bootstrap 4 Alpha blog post](http://blog.getbootstrap.com/2015/08/19/bootstrap-4-alpha/)
* [Bootstrap Themes](http://themes.getbootstrap.com/products/)