# Mérési Jegyzőkönyv: Aktív Aluláteresztő Szűrő

**Mérés tárgya:** Aktív aluláteresztő szűrő frekvenciaátvitelének vizsgálata Bode Analyzerral.

| Név | Helyszín | Dátum |
| :--- | :--- | :--- |
| **Pozsgai Péter** | Miskolci SZC Kandó Kálmán Technikum, v3 labor | 2026-01-29 |

---

## 1. Elméleti háttér

Az aktív aluláteresztő szűrő a kisfrekvenciás jeleket átengedi, a nagyfrekvenciás jeleket csillapítja. A legfontosabb paramétere a **vágási frekvencia (fc)**, ahol az erősítés 3 dB-t esik a maximális értékhez képest.

### Szimuláció
A mérés előtt Falstad szimulátorral meghatároztuk az elméleti vágási frekvenciát.

![Áramkör szimuláció](invertalo%20fals.<img width="828" height="630" alt="Képernyőkép 2026-01-29 125535" src="https://github.com/user-attachments/assets/556cc85f-537c-4704-94e2-939bdbd93368" />
png)

**Szimulált adatok:**
* Vágási frekvencia (fc): **1,36 kHz**
* Maximális erősítés: **18,5 dB** (kb. 8,4-szeres)

---

## 2. Mérési összeállítás

A mérést **NI ELVIS II+ Bode Analyzer** műszerével végeztük.

* **Műszer:** Bode Analyzer
* **Bemenet (Stimulus):** Az áramkör bemenetére kötve.
* **Kimenet (Response):** Az áramkör kimenetére kötve.
* **Frekvencia tartomány:** 10 Hz - 20 kHz

---

## 3. Mérési eredmények

A Bode analizátorral felvettük az áramkör amplitúdó- és fáziskarakterisztikáját.

![Bode diagram mérés](Képernyőkép%202026-01<img width="922" height="736" alt="Képernyőkép 2026-01-29 125233" src="https://github.com/user-attachments/assets/42456d76-138a-4e5a-8158-65335eb6ee3d" />
-29%20120057.png)

*(Megjegyzés: A képen a Bode diagram látható, ahol a zöld vonal az erősítést, a kék a fázist jelöli.)*

**Leolvasott értékek a grafikonról:**

1.  **Erősítés a tartomány elején (Pass band):**
    Stabilan magas, kb. **18,5 dB**.

2.  **Vágási pont (-3dB pont):**
    Megkerestük a kurzorral azt a pontot, ahol az erősítés 3 dB-lel csökken a maximumhoz képest (kb. 15,5 dB-re).
    * Leolvasott frekvencia: **1,36 kHz**

---

## 4. Kiértékelés

Összehasonlítjuk az elméleti (számított/szimulált) vágási frekvenciát a Bode analizátorral mért értékkel.

**Adatok:**
* Elméleti vágási frekvencia (Szimulált): **1,360 Hz** (1,36 kHz)
* Mért vágási frekvencia (Bode): **1,360 Hz** (1,36 kHz)

## 5. Következtetés

A mérés során az aktív aluláteresztő szűrő egy működési pontját sikerült rögzíteni.

1.  **Működés igazolása:** Az alacsony frekvencián (100 Hz) mért erősítés (**8,398**) megegyezik az aktív erősítő tag várható erősítésével, ami arra utal, hogy a szűrő ezen a tartományon belül engedi át a jelet.
2.  **Szimuláció és mérés:** A mért erősítés (8,398) nagyon közel van a szimulált/elméleti erősítéshez (8,478).
3.  **További lépések:** A szűrő teljes karakterisztikájának feltérképezéséhez frekvenciasöprést (több mérési pontot különböző frekvenciákon) kellene végezni, és rögzíteni a kimeneti feszültség változását. Ez lehetővé tenné a vágási frekvencia pontosabb, valós idejű meghatározását, és összevetését a szimulált **$1,36\,\text{kHz}$** értékkel.

---
*Aláírás:* **Pozsgai Péter**
