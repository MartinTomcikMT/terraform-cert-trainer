# Terraform Cert Trainer 1.0
Neoficiálny študijný MVP pre HashiCorp Terraform Associate (004), Terraform 1.12.

## Spustenie / GitHub Pages
Rozbaľ ZIP do koreňa repozitára, nahraj všetky produkčné súbory (index.html, style.css, app.js, content.json, sw.js, manifest.webmanifest a ikony). Settings → Pages → Deploy from a branch → main → / (root). Lokálne v rozbalenom adresári spusti `python3 -m http.server 8000` a otvor http://localhost:8000. Nie cez file://. Bez backendu, bez cloud deploymentu.

## Aktualizácia z Preview
1. V Preview exportuj JSON zálohu.
2. Nahraď produkčné súbory novými na rovnakej URL. Zachovaný názov IndexedDB `tf-cert-trainer`, store `progress`, kľúč `current` a všetkých 37 pôvodných ID otázok.
3. Obnov stránku; pri starom obsahu použi Ctrl+F5. Ak sa zmenila URL/origin, importuj zálohu ručne. Staré odpovede sa prenesú, no levely musia byť absolvované v novom systéme.
4. Pred každou ďalšou aktualizáciou exportuj zálohu. Import nahrádza progres, nie obsah. Reset progresu zachová obsah; reset databázy odstráni lokálny progres a cache. Pri resete zatvor ostatné karty aplikácie.

## Obsah a funkcie
- 8 oblastí, 37 oficiálnych objectives, 37 výučbových a 11 opakovacích levelov, 185 konceptov, 601 cvičení vrátane variantov.
- 15 otázok na level, hranica 12/15, vysvetlenie, opakovanie chýb, odomykanie a história.
- Practice bez obmedzenia levelmi, filtre oblasť/objective/typ/obtiažnosť/chyby. Pri malom výbere sa použije dostupný počet bez duplikácie ID.
- Single choice, multiple answer, true/false, presné doplnenie, poradie. Doplnenie porovnáva presný text po normalizácii medzier; synonymá zatiaľ nehodnotí.
- IndexedDB, import/export, PWA manifest a offline cache po prvom úspešnom načítaní. Offline dostupnosť závisí od prehliadača; externé dokumentačné odkazy vyžadujú internet.
- Upevnenie konceptu: minimálne dve rôzne ID s poslednou správnou odpoveďou a žiadne posledné nesprávne odpovede. Nejde o dôkaz dlhodobého zapamätania.

## Zdroje
https://developer.hashicorp.com/certifications/terraform-associate
https://developer.hashicorp.com/terraform/tutorials/certification-004/associate-review-004
https://developer.hashicorp.com/terraform/tutorials/certification-004/associate-study-004
Otázky sú originálne tréningové varianty, nie exam dumps. Odkazy sú tematické a neboli individuálne overené pre každú otázku. HCL ukážky sú ilustračné fragmenty, nie výsledok reálneho Terraform CLI.

## Kontroly a limity
Node --check app.js a sw.js úspešné; kontrola JSON, unikátnych ID, väzieb a odpovedí úspešná. Chromium/Playwright pokus zlyhal na ERR_BLOCKED_BY_ADMINISTRATOR pri lokálnej URL, preto interakcie, migrácia, PWA a offline režim nie sú end-to-end overené. Kompletný odborný audit otázok neprebehol. Databáza ešte nedosahuje cieľ 1500 otázok; obsahuje varianty rovnakých konceptov. Adaptívne opakovanie, denné úlohy, achievements, simulátor, samostatné CLI/HCL tréningy a labs patria do ďalších verzií.
