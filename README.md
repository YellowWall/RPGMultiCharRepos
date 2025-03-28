***_Spunaspila vefþjónusta_***

Áætlun hér er að skrifa vefþjónustu í kotlin til að halda utan um karaktera fyrir spunaspil. Eftirfarandi atriði eiga að vera útfærð:
1. Almennt utanumhald fyrir karakter á þeim forsendum að allir karakterara hafa nafn, eiginleika, inventory, baksögu/punkta, leikjakerfi sem þeir eru spilaðir í og spilara
2. Notendakerfi svo að notendur geti skapað karaktera sína og haldið utan um þá á einum stað
3. Leikjastjórnenda interface
4. skilaboðavirkni bundin við leiki


**Notendakerfi**

Allir notendur skrá sig inn með lykilorði. Lykilorð skulu ekki vera geymd,
einungis hash lykilorða skal vera geymt og gerður samanburður á milli hash af lykilorði notað til innskráningar og hash af lykilorði notanda.

Allir notendur hafa sömu eiginleika í vefþjónustu og munu geta séð lista af leikjum sem karakterar þeirra tilheyra.

Vinakerfi skal vera til staðar svo að notendur geti haldið skrá yfir aðra vini sýna sem nota forritið. Auk annarar virkni.

**Leikir og karakterar**

Karakterar skulu vera bundnir við leiki og leikjakerfi, notandi skal hafa getuna til að færa karaktera milli leikja með þeirri takmörkun að karakter getur ekki farið í annað leikjakerfi.

Þegar notandi færir karakter milli leikja skal hann hafa getuna til að afrita karakter yfir í nýjan leik án tengingar við gamla leikinn eða með tengingu við upprunalega leikinn.
Með þessu er átt við að breytingar sem eru gerðar á karakternum í nýjan leiknum, t.d. breytingar á eiginleikum eða baksögu, geta annaðhvort haldist fyrir báða leiki eða verið takmarkað við leikinn þar sem breytingarnar eiga sér stað.

Notandi á að geta skoðað bæði þá leiki sem hann er hluti af, hvort sem spilari eða leikjastjórnandi. Notendur skulu hafa getuna til að leyfa öðrum notendum að sjá leiki sína eða halda þeim leyndum, með getuna til að halda öllum leikjum sínum leyndum fyrir öllum, hafa þá sýnilega fyrir vini eða sýnilega öllum. Notendur skulu geta valið leynd fyrir prófíl sinn sem heild eða fyrir staka leiki og karaktera með getunni til að breyta þessari leynd hvenær sem er.

**eiginleikar karaktera**

Þar sem að eiginleikar karaktera eru bundnir við leikjakerfi og geta verið breytilegir á mismunandi hátt skal interface vera skapað fyrir eiginleika.

Eiginleikar sem eiga það til að breytast fljótt, t.d. hit points, mana, sanity, skulu vera breytilegir af eiganda karakters án samþykkis leikjastjórnenda en takmarkaðir af öðrum tengdum eiginileikum (þetta gengur og gerist í flestum leikjum). Interface skal vera gert til að reikna hámark þessara eiginleika byggt á eiginleikum karaktera sem eru almennt fastari, t.d. strength, agility, constitution.

Eiginleikar sem eiga að vera minna breytilegir t.d. strength, constitution. Skulu krefjast samþykki frá leikjastjórnenda fyrir breytingum, en skulu hafa "modified" reit fyrir tímabundnar breytingar sem notandi gæti viljað skrá sjálfur í miðjum leik.

**Leikjastjórnendur**

Notendur skulu hafa getuna til að skapa nýja leiki og bjóða öðrum notendum að skapa karaktera í þessum leikjum. Notendur skulu vera skráðir sjálfkrafa sem leikjastjórnendur fyrir þá leiki sem þeir skapa, en skulu hafa getuna til að bjóða öðrum að vera leikjastjórnandi auk þess að afskrá sig sem leikjastjórnendur.

Leikjastjórnendur munu funkera sem admin fyrir sína leiki með getuna til að hafa áhrif á karaktera spilara sinna.

Leikjastjórnendur skulu geta stillt ýmsa hluti, t.d. hvort að spilarar þurfi samþykki þeirra til að breyta eiginileikum karaktera sinna eftir að þeir eru skapaðir.

**leikjakerfi**

Vefþjónusta skal hafa stuðning fyrir meira en eitt leikjakerfi. Fyrir fyrstu útgáfu skal vera til staðar stuðningur fyrir Mork Borg leikjakerfið og Paranoia XP leikjakerfið.

Það er spurning hvort að notendur skuli hafa getuna til að setja inn leikjakerfa interface, en það er seinni tíma vandamál.

**skilaboð**

Vefþjónusta skal hafa skilaboðakerfi. Skilaboð skulu vera skilgreind sem almenn skilaboð til notanda eða bundin við leik.

Skilaboðakerfi skal styðja bæði hópspjall og einstaklingsskilaboð.

Spurning um hvort að við viljum bara nota module sem er þegar til og opensource, sjáum til. Þetta er ekki high priority.

**changelog**

Til staðar skal vera changelog fyrir karaktera og leiki.
