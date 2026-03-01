# 📘 Návod pro práci s repozitářem `data-contracts`

Tento dokument je určen všem členům týmů, kteří budou přispívat do repozitáře s Data Contracty. Přečti si ho celý před tím, než začneš pracovat.

---

## 📋 Obsah

1. [Co je GitHub a jak funguje?](#1-co-je-github-a-jak-funguje)
2. [Základní pojmy](#2-základní-pojmy)
3. [Jak se přihlásit a dostat přístup](#3-jak-se-přihlásit-a-dostat-přístup)
4. [Jak nahrát nebo upravit Data Contract](#4-jak-nahrát-nebo-upravit-data-contract)
5. [Jak vytvořit Pull Request](#5-jak-vytvořit-pull-request)
6. [Jak schválit Pull Request](#6-jak-schválit-pull-request)
7. [Pravidla repozitáře](#7-pravidla-repozitáře)
8. [Ukázka Data Contractu v YAML](#8-ukázka-data-contractu-v-yaml)
9. [Časté chyby a jak je opravit](#9-časté-chyby-a-jak-je-opravit)

---

## 1. Co je GitHub a jak funguje?

GitHub je platforma pro sdílení a správu souborů (v našem případě Data Contractů). Funguje jako sdílená složka, ale s jedním velkým rozdílem — **každá změna je zaznamenána, kdo ji udělal a kdy**. Nikdy nemůžeš omylem smazat práci někoho jiného, protože vše je verzované.

Náš repozitář se jmenuje **`data-contracts`** a je uložen v GitHub Organization **`bank-data-contracts`**.

---

## 2. Základní pojmy

| Pojem | Vysvětlení |
|---|---|
| **Repozitář (repo)** | Složka se všemi soubory projektu |
| **Branch (větev)** | Kopie repozitáře, kde pracuješ izolovaně |
| **Commit** | Uložení změn s popisem co jsi změnil |
| **Pull Request (PR)** | Žádost o přidání tvých změn do hlavní větve |
| **Merge** | Sloučení tvých změn do hlavní větve `main` |
| **main** | Hlavní, oficiální větev — vždy stabilní |
| **CODEOWNERS** | Soubor, který určuje kdo schvaluje změny v jaké složce |

---

## 3. Jak se přihlásit a dostat přístup

### Krok 1 — Vytvoř si GitHub účet
1. Jdi na [github.com](https://github.com)
2. Klikni na **"Sign up"**
3. Vyplň email, heslo a uživatelské jméno
4. Potvrď email

### Krok 2 — Pošli své GitHub username správci
- Pošli své GitHub **username** (ne email) správci repozitáře (JalovecM)
- Správce tě přidá do Organization a do tvého týmu
- Dostaneš emailovou pozvánku — **musíš ji přijmout!**

### Krok 3 — Přijmi pozvánku
1. Zkontroluj email
2. Klikni na odkaz v pozvánce
3. Klikni **"Accept invitation"**

---

## 4. Jak nahrát nebo upravit Data Contract

> ⚠️ **NIKDY nepracuj přímo v `main` větvi!** Vždy si vytvoř vlastní branch.

### Krok 1 — Otevři repozitář
Jdi na: `https://github.com/bank-data-contracts/data-contracts`

### Krok 2 — Vytvoř novou branch
1. Klikni na tlačítko **`main`** vlevo nahoře (šedé tlačítko s ikonou větve)
2. Do textového pole napiš název své větve, například:
   ```
   feature/team6-strategy-datacontract
   ```
   > Konvence pojmenování: `feature/<nazev-tymu>-<co-delas>`
3. Klikni na **"Create branch: feature/..."**

### Krok 3 — Přejdi do složky svého týmu
Klikni na složku svého týmu, například `team6-strategy`

### Krok 4a — Nahraj nový soubor
Pokud nahráváš nový Data Contract:
1. Klikni na **"Add file"** → **"Upload files"**
2. Přetáhni soubor `datacontract.yml` do okna
3. Zkontroluj, že jsi ve správné branch (ne v `main`!)
4. Do pole **"Commit changes"** napiš popis, například:
   ```
   Add strategy datacontract v1.0
   ```
5. Klikni **"Commit changes"**

### Krok 4b — Uprav existující soubor
Pokud upravuješ existující Data Contract:
1. Klikni na soubor `datacontract.yml`
2. Klikni na **ikonu tužky** (Edit) vpravo nahoře
3. Proveď změny
4. Dole vyplň popis změny, například:
   ```
   Update schema fields in strategy datacontract
   ```
5. Zkontroluj, že je vybrána možnost **"Commit directly to `feature/...`"** (tvoje branch, ne main!)
6. Klikni **"Commit changes"**

---

## 5. Jak vytvořit Pull Request

Po commitu je potřeba požádat o začlenění změn do `main`. To se dělá přes **Pull Request**.

### Krok 1
Po commitu GitHub automaticky zobrazí žlutý banner:
> *"Your branch had recent pushes — Compare & pull request"*

Klikni na zelené tlačítko **"Compare & pull request"**

### Krok 2 — Vyplň Pull Request
- **Title:** Stručný název, např. `Add strategy datacontract v1.0`
- **Description:** Popiš co jsi přidal/změnil, např.:
  ```
  Přidán první datacontract pro Tým 6 - Strategie.
  Obsahuje schema pro tabulku dp_strategy_kpi.
  Verze: 1.0.0
  ```

### Krok 3
Klikni na zelené tlačítko **"Create pull request"**

### Krok 4 — Počkej na schválení
- GitHub automaticky přiřadí reviewera z tvého týmu (díky CODEOWNERS)
- Reviewer dostane emailové upozornění
- Po schválení klikni **"Merge pull request"** → **"Confirm merge"**

---

## 6. Jak schválit Pull Request

Pokud jsi byl označen jako reviewer:

1. Jdi do záložky **"Pull requests"** v repozitáři
2. Klikni na Pull Request který máš schválit
3. Klikni na záložku **"Files changed"** — prohlédni si co bylo změněno
4. Klikni na zelené tlačítko **"Review changes"**
5. Vyber jednu z možností:
   - ✅ **"Approve"** — změny jsou v pořádku, schvaluji
   - 💬 **"Comment"** — mám komentář, ale neschvaluji ani nezamítám
   - ❌ **"Request changes"** — jsou potřeba opravy
6. Klikni **"Submit review"**

---

## 7. Pravidla repozitáře

| Pravidlo | Popis |
|---|---|
| ✅ Pracuj vždy ve vlastní branch | Nikdy ne přímo v `main` |
| ✅ Každý tým spravuje svou složku | Neupravuj soubory v složkách jiných týmů |
| ✅ Pojmenuj branch správně | `feature/<tym>-<popis>` |
| ✅ Piš smysluplné commit zprávy | Ne jen "update" nebo "fix" |
| ✅ Každý PR musí být schválen | Minimálně 1 schválení je povinné |
| ❌ Nikdy nepush přímo do `main` | Bude zablokováno systémem |
| ❌ Neupravuj CODEOWNERS ani .github | Pouze správce repozitáře |

---

## 8. Ukázka Data Contractu v YAML

Níže je ukázka kompletního Data Contractu. Zkopíruj ho, ulož jako `datacontract.yml` do složky svého týmu a vyplň hodnoty pro váš datový produkt.

```yaml
# ============================================================
# DATA CONTRACT - UKÁZKA / ŠABLONA
# ============================================================
dataContractSpecification: 1.1.0

# Unikátní identifikátor data produktu
id: urn:businessdomain:nova-banka:strategy:monthly-kpi-report

info:
  title: DP_STRATEGY_MONTHLY_KPI          # Název data produktu (velká písmena)
  name: Strategy Monthly KPI Report        # Čitelný název
  maturity_score: 60%                      # Vyspělost produktu (0-100%)
  version: 1.0.0                           # Verze ve formátu major.minor.patch
  status: in development                   # Možnosti: draft / in development / active / deprecated

  description: |
    Data produkt obsahuje měsíční KPI reporty pro tým Strategie.
    Zahrnuje finanční ukazatele, výkonnostní metriky a strategické cíle banky.
    Data latency: D + 1 (data jsou dostupná den po zpracování)

    Filter Rules:
    * Pouze záznamy s platným business_date
    * Region musí být CZ nebo SK

    Use Cases:
    * UC1 - Sledování měsíčního plnění strategických KPI
    * UC2 - Porovnání výkonu napříč obchodními jednotkami

  owner: Nova Banka \ Team6 \ Strategy
  contact:
    name: Jan Novák
    email: jan.novak@nova-banka.cz

# ============================================================
# SERVERY - kde jsou data fyzicky uložena
# ============================================================
servers:
  PRODUCTION:
    type: databricks                        # Typ databáze
    host: nova-banka-prod.cloud.databricks.com
    environment: production
    catalog: datamesh-nova-banka-prod
    schema: strategy-prod
    table: dp_strategy_monthly_kpi

  DEVELOPMENT:
    type: databricks
    host: nova-banka-dev.cloud.databricks.com
    environment: development
    catalog: datamesh-nova-banka-dev
    schema: strategy-dev
    table: dp_strategy_monthly_kpi

# ============================================================
# SCHEMA - struktura dat (tabulky a sloupce)
# ============================================================
schema:
  - name: dp_strategy_monthly_kpi
    description: Měsíční KPI tabulka pro strategické reportování
    fields:

      - name: record_id
        type: string
        description: Unikátní identifikátor záznamu (UUID)
        required: true
        unique: true
        example: "550e8400-e29b-41d4-a716-446655440000"

      - name: business_date
        type: date
        description: Datum záznamu ve formátu YYYY-MM-DD
        required: true
        example: "2024-01-31"

      - name: region
        type: string
        description: Region - povolené hodnoty CZ nebo SK
        required: true
        enum: [CZ, SK]
        example: "CZ"

      - name: kpi_name
        type: string
        description: Název KPI ukazatele
        required: true
        example: "Net_Interest_Margin"

      - name: kpi_value
        type: decimal
        description: Hodnota KPI ukazatele
        required: true
        example: 2.35

      - name: kpi_target
        type: decimal
        description: Cílová hodnota KPI
        required: false
        example: 2.50

      - name: currency
        type: string
        description: Měna - ISO 4217 kód
        required: false
        example: "CZK"

      - name: created_at
        type: timestamp
        description: Čas vytvoření záznamu
        required: true
        example: "2024-01-31T08:00:00Z"

# ============================================================
# KVALITA DAT - pravidla pro validaci
# ============================================================
quality:
  - rule: not_null
    field: record_id
    description: ID záznamu nesmí být prázdné

  - rule: not_null
    field: business_date
    description: Datum záznamu nesmí být prázdné

  - rule: unique
    field: record_id
    description: Každý záznam musí mít unikátní ID

  - rule: accepted_values
    field: region
    values: [CZ, SK]
    description: Region musí být CZ nebo SK

  - rule: not_null
    field: kpi_value
    description: Hodnota KPI nesmí být prázdná

# ============================================================
# SLA - dohoda o úrovni služeb
# ============================================================
sla:
  availability: 99.5%                      # Dostupnost dat
  data_latency: D+1                        # Zpoždění dat
  retention_period: 36 months             # Jak dlouho jsou data uchovávána
  support_contact: jan.novak@nova-banka.cz
```

---

## 9. Časté chyby a jak je opravit

### ❌ "Merging is blocked"
**Příčina:** Pull Request nemá požadované schválení.
**Řešení:** Požádej kolegu z tvého týmu aby PR schválil.

### ❌ Commitoval jsem přímo do `main`
**Příčina:** Nezvolil jsi vlastní branch před commitem.
**Řešení:** Vytvoř novou branch, přenes změny a otevři PR. Požádej správce o pomoc.

### ❌ Nahrál jsem soubor do špatné složky
**Příčina:** Nebyl jsi ve složce svého týmu.
**Řešení:** Smaž soubor ze špatné složky, nahraj ho do správné a vytvoř PR.

### ❌ YAML soubor má chybu ve formátování
**Příčina:** YAML je citlivý na odsazení (mezery).
**Řešení:** Použij online validátor na [yamllint.com](https://www.yamllint.com) před nahráním.

---

## 💬 Potřebuješ pomoct?

Kontaktuj správce repozitáře nebo otevři **Issue** v repozitáři:
1. Klikni na záložku **"Issues"**
2. Klikni **"New issue"**
3. Popiš svůj problém

---

*Dokument vytvořen pro školní projekt Nova Banka — Data Mesh repozitář.*
