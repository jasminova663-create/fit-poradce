# Fit Poradce - Aplikace pro odhad kalorií

## 📖 Přehled
Aplikace **Fit Poradce** je asistent pro zdravou výživu, který odhaduje kalorie z popisu jídla a doporučuje jídelníček na zbytek dne.

---

## 🎯 Modelový uživatel
- **Pohlaví:** Muž
- **Věk:** 50 let
- **Výška:** 190 cm
- **Hmotnost:** 105 kg
- **Zaměstnání:** Sedavé

### Výpočet kalorických potřeb:
1. **BMR (Basal Metabolic Rate)** - Harris-Benedictův vzorec:
   ```
   BMR = 88.362 + (13.397 × 105) + (4.799 × 190) - (5.677 × 50)
   BMR ≈ 2 125 kcal/den
   ```

2. **TDEE (Total Daily Energy Expenditure)** - s faktor 1.375 (sedavá práce):
   ```
   TDEE = 2 125 × 1.375 ≈ 2 920 kcal/den
   ```

**→ Doporučené denní příjmení: ~2 900 kcal**

---

## 🚀 Jak aplikaci používat

### Skill 1: Odhad kalorií z popisu jídla

**Příkaz:** Cokoliv, co chcete zkonzumovat

**Příklad:**
```
Snědl jsem: 200g kuřecího prsou, 150g rýže a hrnek řeckého jogurtu
```

**Postup:**
1. Uživatel popíše, co snědl/pil
2. Vy rozhodete popis na jednotlivé položky
3. Pro každou položku odhadnete přibližné kalorie na základě:
   - Standardních nutričních tabulek
   - Uvedeného množství (grams, porce, šálky, atd.)
   - Typu přípravy (pečené, smažené, vařené)
4. Sečtete a vraťte celkový odhad

**Příklad odpovědi:**
```
📊 ODHAD KALORIÍ
─────────────────
Kuřecí prsa (200g, pečené): 330 kcal
Rýže (150g, vařená): 195 kcal
Řecký jogurt (250ml): 150 kcal

✅ CELKEM: 675 kcal
```

---

### Skill 2: Doporučení jídelníčku na zbytek dne

**Příkaz:** Jaký mám mít jídelníček na zbytek dne?

**Vstupní data:**
- Modelový uživatel má cíl: **~2 900 kcal za den**
- Známe, kolik kalorií už snědl (z předchozího odhadu)
- Zbývající kalorie = 2 900 - už zkonzumované

**Postup:**
1. Spočítejte zbývající kalorie
2. Navrhněte konkrétní jídla/nápoje na zbytek dne
3. Rozdělte na jednotlivé porce s odhady kalorií
4. Zaměřte se na vyvážení (proteiny, sacharidy, tuky)

**Příklad odpovědi:**
```
🎯 DOPORUČENÍ NA ZBYTEK DNE
──────────────────────────

Dosud: 675 kcal
Zbývá: 2 225 kcal
Čas: 15:00 - zbývá večeře a případné svačiny

💡 NAVRH MENU:

ODPOLEDNE (16:00):
├─ Apple (1 středně velké): 95 kcal
└─ Arašídové máslo (1 lžíce): 95 kcal
  → Odpoledne: 190 kcal

VEČEŘE (19:00):
├─ Losos (180g, pečený): 350 kcal
├─ Brambory (200g, vařené): 160 kcal
├─ Brokolice (150g): 50 kcal
└─ Olivový olej (1 lžíce na přípravu): 120 kcal
  → Večeře: 680 kcal

VEČER (21:00):
└─ Herbal čaj bez cukru: 0 kcal

─────────────────
CELKEM ZBÝVAJÍCÍHO: 870 kcal
ZBUDE NA REZERVU: ~485 kcal
```

---

## 💾 Datové zdroje

### Typické kalorie (pro rychlý odhad):

**Proteiny:**
- Kuřecí prsa (1kg) = 1650 kcal
- Ryby (1kg) = 1400-2000 kcal
- Vejce (1 kus) = 155 kcal
- Řecký jogurt (250ml) = 150 kcal

**Sacharidy:**
- Rýže (1kg suchá) = 3650 kcal → 195 kcal/150g vařená
- Chléb (1 krajíc) = 80 kcal
- Ovoce (průměr) = 80-150 kcal/porce
- Zelenina = 20-50 kcal/porce

**Tuky:**
- Olivový olej (1 lžíce/15ml) = 120 kcal
- Máslo (1 lžíce) = 100 kcal
- Arašídové máslo (1 lžíce) = 95 kcal

**Nápoje:**
- Voda, čaj bez cukru = 0 kcal
- Mléko (250ml, tučné) = 160 kcal
- Soda, džus (250ml) = 110-150 kcal
- Pivo (330ml) = 150 kcal

---

## ⚙️ Konfigurace

### Změna uživatele
Pokud se změní profil uživatele, recalculejte:

```
1. Vážu × (88.362 + 13.397 × W + 4.799 × H - 5.677 × V) = BMR
   (W=váha kg, H=výška cm, V=věk let)

2. BMR × Faktor aktivity:
   - Velmi sedavá (málo pohybu): 1.2
   - Sedavá (kancelářská práce): 1.375
   - Středně aktivní (2-3x/týdně sport): 1.55
   - Aktivní (5-6x/týdně sport): 1.725
   - Velmi aktivní (denně sport): 1.9

3. TDEE = BMR × Faktor
```

---

## 📝 Poznámky

- **Přesnost:** Odhady jsou orientační (±10-15%), ne přesná věda
- **Alkohol:** 1g = 7 kcal (více než proteiny a sacharidy)
- **Voda:** Nezvyšuje kalorický příjmení, ale pomáhá se sytostí
- **Motivace:** Cíl není být dokonalý, ale udržitelný
- **Fluktuace:** Váha se mění na základě zadržování vody a stolu potravy

---

## 🔗 Soubory

- **index.html** - Vstupní stránka (pro reklamy, GitHub Pages)
- **CLAUDE.md** - Toto, instrukce a skills pro aplikaci

---

## 🚀 Spuštění

Aplikace běží zcela v Claude Code. Prostě:

1. Napište, co jste snědli → odhad kalorií
2. Zeptejte se na doporučení → návrh jídelníčku na zbytek dne
3. Opakujte podle potřeby

Bez backendu, bez databází, bez složitosti.

---

**Vytvořeno:** 2026-09-22
**Verze:** 1.0
**Status:** ✅ Připraveno k použití
