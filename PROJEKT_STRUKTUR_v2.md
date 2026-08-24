[PROJEKT_STRUKTUR.md](https://github.com/user-attachments/files/31387076/PROJEKT_STRUKTUR.md)
# 🗂️ Vollständige Dokumentation: Struktur deines autonomen Claude KI-Departments

Diese Dokumentation bildet die **vollständige, lückenlose Architektur** deines Systems ab. Sie zeigt dir exakt auf, wo sich die **Konfiguration (Config)**, die **Pipeline-Verzeichnisse** und alle anderen strategischen Komponenten befinden, die in deinen PDF-Originalhandbüchern spezifiziert sind.

---

## 🌲 Die visuelle Gesamtstruktur (ASCII-Baum)

Wenn du das Skript `recreate_project_v3.py` ausführst, wird genau diese Struktur direkt auf deinem Mac-Schreibtisch angelegt:

```text
Building Autonomous AI Department/
├── 00_СТАРТ-В-CLAUDE-DESKTOP.md        # Zentraler Start-Prompt für Claude Desktop
├── 02_ПРОМПТЫ.md                       # Master-Prompt-Datenbank aller Agenten
├── 03_ЭКСПЕРИМЕНТЫ.md                  # Test-Sandkasten für Prompt-Modifikationen
├── 04_ЧЕКЛИСТ-СЪЁМКИ.md                # Video- und Foto-Produktionsvorgaben
├── 05_КАРТОЧКА-СРАВНЕНИЯ.md            # Standardisierte Wettbewerbsanalyse-Matrix
├── 06_ИСТОЧНИКИ.md                     # Die unbestechliche Whitelist für Fakten
├── 07_ОТЧЁТ-ПРОВЕРКИ.md                # Prüfberichte und Veto-Logs des QA Critics
├── README.md                           # System-Manifest und Installationsanleitung
├── LICENSE                             # MIT-Lizenz für dein Repository
├── recreate_project_v3.py              # Der vollständige Python-Installer
│
├── 01_ПРОЕКТ-ОТДЕЛА/                   # === OPERATIVER AGENTEN-BEREICH ===
│   ├── .claude/
│   │   └── settings.json               # ⚙️ DIE ZENTRALE SYSTEM-CONFIG (Konfiguration)
│   ├── ЗАДАЧА.md                       # Das übergeordnete Zieldokument des Departments
│   ├── AGENTS.md                       # Rollenspezifikation der 5 Micro-Identitäten
│   ├── employees/                      # System-Prompts der einzelnen Mitarbeiter
│   │   ├── manager/instructions.md     # Managing Director (Orchestrator)
│   │   ├── researcher/instructions.md  # Fact-Finding Researcher (3 Instanzen)
│   │   ├── marketer/instructions.md    # Strategic Marketer
│   │   ├── copywriter/instructions.md  # Emotion-driven Copywriter
│   │   └── critic/instructions.md      # Uncompromising QA Critic
│   ├── output/                         # Dynamischer Zwischenarbeitsbereich der Agenten
│   │   ├── researcher/                 # Berichte (source-1.md, source-2.md, source-3.md)
│   │   ├── marketer/                   # Positionierungsstrategie (strategy.md)
│   │   └── copywriter/                 # Entwürfe & Historie (texts.md)
│   └── final/                          # Verifiziertes Endarchiv für freigegebene Kampagnen
│       └── test-run.md                 # Erfolgreicher, freigegebener Testlauf
│
├── 02_ПРОЕКТ-ПАПКИ-НЕ-АГЕНТЫ/          # === STATISCHE WISSENSDATENBANK ===
│   ├── readme.md                       # Erläuterung der statischen Verzeichnisse
│   ├── knowledge/                      # Globale Leitplanken & Brand Voice
│   │   ├── global/
│   │   │   └── brand_voice_template.md # Schreibstil-Regeln (kurze Sätze, direktes "Du")
│   │   └── copywriter/
│   │       └── forbidden_phrases_template.md # 🚫 Blacklist verbotener KI-Klischees
│   └── pipeline/                       # 🚀 DIE PIPELINE (Zentraler operativer Kern)
│       ├── input/                      # Kampagnen-Input
│       │   ├── briefing_template.md    # Blanko-Vorlage für neue Kampagnen
│       │   └── briefing.md             # Aktives Briefing für deinen KI-Telefonassistenten
│       └── interim/                    # Temporärer Speicher während der Datenverarbeitung
│
└── 03_ИЗМЕНЕНИЕ_ДЛЯ_ТРЕТЬЕГО_РАУНДА/   # === REVISIONS- & OPTIMIERUNGS-PROTOKOLL ===
    ├── readme.md                       # Übersicht der Optimierungsrunden
    └── ИЗМЕНЕНИЕ-01.md                 # Verschärfte Critic-Richtlinien zur System-Kalibrierung
```

---

## ⚙️ 1. Die Konfiguration (Die Config)

Die zentrale Steuerungseinheit deines Systems befindet sich im versteckten Verzeichnis `.claude/` innerhalb der Projekt-Abteilung:
📍 **Pfad:** `01_ПРОЕКТ-ОТДЕЛА/.claude/settings.json`

Diese Datei legt die technischen und pfadbezogenen Spielregeln für Claude Code fest:

```json
{
  "project_name": "subagents_department",
  "version": "1.1.0",
  "default_model": "claude-3-5-sonnet",
  "features": {
    "parallel_research_instances": 3,
    "automatic_veto_handling": true,
    "strict_censorship_enforcement": true
  },
  "paths": {
    "prompts": "02_ПРОМПТЫ.md",
    "critic_rules": "03_ИЗМЕНЕНИЕ_ДЛЯ_ТРЕТЬЕГО_РАУНДА/ИЗМЕНЕНИЕ-01.md",
    "output_directory": "01_ПРОЕКТ-ОТДЕЛА/output/",
    "pipeline_input": "02_ПРОЕКТ-ПАПКИ-НЕ-АГЕНТЫ/pipeline/input/",
    "pipeline_interim": "02_ПРОЕКТ-ПАПКИ-НЕ-АГЕНТЫ/pipeline/interim/"
  }
}
```

*   **`features`:** Aktiviert fortgeschrittene Funktionen wie das parallele Abrufen von drei Recherche-Instanzen zur Vermeidung von kognitiven Verzerrungen (Bias) sowie das automatisierte Veto-Handling.
*   **`paths`:** Sagt Claude Code exakt, wo er seine globalen Anweisungen (`prompts`), die aktuellen Revisions-Regeln (`critic_rules`) und den operativen Input (`pipeline_input`) herholen muss.

---

## 🚀 2. Die Pipeline (Zentraler Kampagnen-Ablauf)

Die Pipeline ist das Herzstück deiner täglichen Arbeit. Sie ist streng vom Agenten-Code getrennt, damit statische Briefings nicht das wertvolle Kontextfenster der Agenten verstopfen.
📍 **Pfad:** `02_ПРОЕКТ-ПАПКИ-НЕ-АГЕНТЫ/pipeline/`

Sie besteht aus zwei Kernbereichen:

### A. `/pipeline/input/`
Hier legst du die Marschroute fest.
*   **`briefing_template.md`:** Eine Blanko-Vorlage, die du für jedes neue Produkt kopieren und ausfüllen kannst.
*   **`briefing.md`:** Das aktuell aktive Arbeitsdokument. Im Moment ist dort ein vollständiges, hochkonvertierendes Praxisbriefing für deinen **KI-Telefonassistenten für Kfz-Betriebe** hinterlegt. Es definiert die Zielgruppe (Inhaber freier Werkstätten), den USP (fängt 100% aller Nacht-Anrufe ab) und verweist auf die verifizierten Quellen-IDs in der Hauptdatenbank.

### B. `/pipeline/interim/`
*   Dieses Verzeichnis dient als temporärer Puffer, in dem Claude Code während des laufenden Prozesses Zwischenstände speichert, analysiert und abgleicht, bevor die Texte endgültig freigegeben werden.

---

## 📦 3. Die anderen wichtigen Komponenten ("and others")

### A. Die Wissensdatenbank (`/knowledge/`)
📍 **Pfad:** `02_ПРОЕКТ-ПАПКИ-НЕ-АГЕНТЫ/knowledge/`
*   **`global/brand_voice_template.md`:** Schreibt die unumstößlichen Schreibregeln für alle Werbematerialien vor (z. B. absolute Text-Pragmatik, maximal 15 Wörter pro Satz, direkte Ansprache des Kunden mit "Du").
*   **`copywriter/forbidden_phrases_template.md`:** Der Zensur-Filter. Begriffe wie *"revolutionär"*, *"ultimativ"* oder *"KI-gestützte Magie"* sind hier gelistet. Verwendet der Copywriter eines dieser Wörter, schlägt der Critic sofort Alarm.

### B. Das Revisions-Protokoll (`03_ИЗМЕНЕНИЕ_ДЛЯ_ТРЕТЬЕГО_РАУНДА/`)
📍 **Pfad:** `03_ИЗМЕНЕНИЕ_ДЛЯ_ТРЕТЬЕГО_РАУНДА/ИЗМЕНЕНИЕ-01.md`
*   Hier werden alle Kalibrierungen des Systems festgehalten. Im aktuellen Dokument ist dokumentiert, wie der Critic im dritten Durchlauf noch schärfere Maßstäbe anlegt (z. B. die Einstufung jeglicher emotionaler Superlative wie "am besten" als sofortigen Blocker).

### C. Die 7 Root-Einstiegsdateien (Aus dem Betriebshandbuch)
📍 **Pfad:** Hauptverzeichnis (Root)
*   **`00_СТАРТ-В-CLAUDE-DESKTOP.md`:** Dein direkter Einstiegsbefehl, um die gesamte Abteilung im Terminal zum Leben zu erwecken.
*   **`02_ПРОМПТЫ.md`:** Das übergeordnete Prompts-Manifest des gesamten Departments.
*   **`03_ЭКСПЕРИМЕНТЫ.md`:** Die Sandbox zur sicheren Erprobung neuer Prompt-Formate.
*   **`04_ЧЕКЛИСТ-СЪЁМКИ.md`:** Das visuelle Regelwerk, um deine fertigen Werbetexte fehlerfrei in TikTok-, Shorts- oder Video-Werbung zu übersetzen.
*   **`05_КАРТОЧКА-СРАВНЕНИЯ.md`:** Die standardisierte Vergleichstabelle für systematische Wettbewerbsanalysen.
*   **`06_ИСТОЧНИКИ.md`:** Das unbestechliche Whitelist-Verzeichnis, auf das sich der Researcher beziehen MUSS.
*   **`07_ОТЧЁТ-ПРОВЕРКИ.md`:** Das Audit-Log, in dem der Critic jedes Veto und jede Freigabe sekundengenau dokumentiert.
