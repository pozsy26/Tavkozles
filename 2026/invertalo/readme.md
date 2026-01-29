# Mérési Jegyzőkönyv: Invertáló Erősítő

**Mérés tárgya:** Invertáló műveleti erősítő alapkapcsolás vizsgálata, a Falstad szimuláció és a valós NI ELVIS mérés összehasonlítása.

| Név | Helyszín | Dátum |
| :--- | :--- | :--- |
| **Pozsgai Péter** | Miskolci SZC Kandó Kálmán Technikum, v3 labor | 2026-01-29 |

---

## 1. Elméleti háttér és Szimuláció

A mérés előtt az áramkör működését Falstad szimulátorral ellenőriztük.
Az áramkör egy **invertáló erősítő**, melynek erősítését ($A_v$) a visszacsatoló ($R_f$) és bemeneti ($R_{in}$) ellenállások aránya határozza meg.

### Kapcsolási rajz és szimulált értékek
A szimulátorban DC feszültséggel vizsgáltuk az átvitelt.

![Falstad áramkör szimuláció](invertalo%20f<img width="1027" height="626" alt="invertalo fals" src="https://github.com/user-attachments/assets/4f056160-c708-404b-973e-368abb18674b" />

* **Bemeneti ellenállás ($R_{in}$):** $11,7\,\text{k}\Omega$
* **Visszacsatoló ellenállás ($R_{f}$):** $99,2\,\text{k}\Omega$
* **Szimulátor által mért kimenő feszültség:** $\mathbf{-8,478\,\text{V}}$ (1 V bemenetnél)
* **Elméleti erősítés:** $A = -8,478$

---

## 2. Mérési összeállítás

A valós mérés során NI ELVIS II+ rendszert használtunk. A bemenetre váltakozó áramú (AC) szinusz jelet kapcsoltunk a függvénygenerátorral.

### Generátor beállításai
* **Jelalak:** Szinusz
* **Frekvencia:** $100\,\text{Hz}$
* **Amplitúdó:** $1,00\,\text{V}_{pp}$
* **Offset:** $0\,\text{V}$

![Függvénygenerátor beállításai](Képernyőkép%202026-01-29%2012<img width="513" height="602" alt="Képernyőkép 2026-01-29 120033" src="https://github.com/user-attachments/assets/5b917de6-6906-47e3-8a9f-0a58e48f61ac" />


---

## 3. Mérési eredmények

Az oszcilloszkópon a sárga csatorna (CH0) a bemeneti jelet, a kék csatorna (CH1) az erősített kimeneti jelet mutatja.

![Oszcilloszkóp mérés](Képernyőkép%202026-01-29%2012<img width="1072" height="742" alt="Képernyőkép 2026-01-29 120057" src="https://github.com/user-attachments/assets/bceeaa1f-244e-4682-ab44-a86a9da63e16" />


### Mért értékek (Oszcilloszkóp)

| Jel | Csatorna | Vpp (Csúcs-csúcs) | RMS (Effektív) | Megjegyzés |
| :--- | :--- | :--- | :--- | :--- |
| **Bemenet** | CH0 (Sárga) | $1,000\,\text{V}$ | $352,75\,\text{mV}$ | Referencia jel |
| **Kimenet** | CH1 (Kék) | **$8,398\,\text{V}$** | $2,965\,\text{V}$ | $180^{\circ}$ fázisban fordított |

---

## 4. Kiértékelés és Hiba számítás

Ebben a részben összehasonlítjuk a szimulátor és a valós mérés eredményeit.

### A. Valós feszültségerősítés
A mért kimeneti és bemeneti feszültség aránya adja meg a valós erősítést.

* Mért Kimenet: **8,398 V**
* Mért Bemenet: **1,000 V**

**Mért Erősítés = 8,398 / 1,000 = 8,398**

### B. Összehasonlítás
A szimulátorban kapott értéket tekintjük a pontos (referencia) adatnak.

* Szimulált erősítés: **8,478** (Elméleti érték)
* Mért erősítés: **8,398** (Valós érték)
* Különbség: **0,08**

### C. Hiba százalékos számítása
Azt vizsgáljuk, hány százalékkal tér el a mérésünk a szimulációtól.

Számítás képlete: (Különbség / Szimulált érték) * 100

* Számítás: (0,08 / 8,478) * 100
* Eredmény: **0,94 %**

**A mérési hiba tehát 1% alatt van (0,94%), ami nagyon pontos mérést jelent.**

## 5. Következtetés

A mérés igazolta az invertáló erősítő működését. A szimulátor által előrejelzett $-8,478$-as erősítést a valós áramkör **1% alatti hibával** ($0,94\%$) produkálta. Az oszcilloszkóp ábráján látható fázisfordítás megfelel az elméleti várakozásoknak.
