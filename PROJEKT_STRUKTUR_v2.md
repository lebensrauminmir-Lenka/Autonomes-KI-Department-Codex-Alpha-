# 🗂️ Vollständige Projekt- und Ordnerstruktur
Dieses Dokument bietet eine lückenlose, detaillierte und vollständig ausformulierte Übersicht über die tatsächliche Dateistruktur deines Claude-Agenten-Departments (`subagents_department`). Es bildet exakt ab, welche Ordner und Dateien durch das Skript `recreate_project.py` erstellt werden.

---

## 🌳 1. Der vollständige Verzeichnisbaum (ASCII-Visualisierung)

Hier ist die exakte und vollständige Struktur deines Projekts. Jede Datei und jeder Unterordner existiert genau an dieser Stelle:

```text
subagents_department/
├── 01_ПРОЕКТ-ОТДЕЛА/
│   ├── .claude/
│   │   └── settings.json
│   ├── employees/
│   │   ├── copywriter/
│   │   │   └── instructions.md
│   │   ├── critic/
│   │   │   └── instructions.md
│   │   ├── marketer/
│   │   │   └── instructions.md
│   │   └── researcher/
│   │       └── instructions.md
│   ├── final/
│   │   └── test-run.md
│   ├── output/
│   │   ├── copywriter/
│   │   │   └── texts.md
│   │   ├── marketer/
│   │   │   └── strategy.md
│   │   └── researcher/
│   │       ├── source-1.md
│   │       ├── source-2.md
│   │       └── source-3.md
│   ├── AGENTS.md
│   └── ЗАДАЧА.md
├── 02_ПРОЕКТ-ПАПКИ-НЕ-АГЕНТЫ/
│   ├── knowledge/
│   │   ├── copywriter/
│   │   │   └── forbidden_phrases_template.md
│   │   └── global/
│   │       └── brand_voice_template.md
│   ├── pipeline/
│   │   └── input/
│   │       └── briefing_template.md
│   └── readme.md
└── 03_ИЗМЕНЕНИЕ_ДЛЯ_ТРЕТ_РАУНДА/
    └── readme.md
```

---

## 📂 2. Detailerklärung aller Verzeichnisse (Ordner-Katalog)

### Bereich 1: `01_ПРОЕКТ-ОТДЕЛА` (Der aktive Agenten-Bereich)
In diesem Hauptordner agieren deine virtuellen Mitarbeiter. Hier liegen die System-Prompts, die Arbeitsverzeichnisse und die fertigen Text-Freigaben.

*   **`subagents_department/01_ПРОЕКТ-ОТДЕЛА/`**: Das operative Zentrum.
*   **`.../.claude/`**: Ein versteckter Systemordner für Claude-Schnittstellen.
    *   `settings.json`: Die zentrale Konfigurationsdatei für das gesamte Department (Modelleinstellungen, aktivierte Features, Datenpfade).
*   **`.../employees/`**: Das „Büro“ deiner Agenten. Enthält pro Rolle einen eigenen Unterordner.
    *   `copywriter/`: Arbeitsplatz des Copywriters. Enthält dessen Systemanweisungen.
    *   `critic/`: Arbeitsplatz des unbestechlichen Qualitätsprüfers (Critic).
    *   `marketer/`: Arbeitsplatz des strategischen Marketing-Spezialisten.
    *   `researcher/`: Arbeitsplatz des faktenbasierten Forschers.
*   **`.../output/`**: Der Zwischenspeicher für noch nicht freigegebene Dokumente. Jeder Agent schreibt seine Ergebnisse in seinen zugeordneten Ordner.
    *   `copywriter/`: Roh- und Entwurfsfassungen der Werbetexte.
    *   `marketer/`: Die ausgearbeitete Marketingstrategie.
    *   `researcher/`: Die verifizierten, faktenbasierten Forschungsberichte.
*   **`.../final/`**: Das Zielverzeichnis. Nur Texte, die die unbestechliche Prüfung des QA Critics fehlerfrei durchlaufen haben, werden hier dauerhaft abgespeichert.

---

### Bereich 2: `02_ПРОЕКТ-ПАПКИ-НЕ-АГЕНТЫ` (Statisches Wissensarchiv)
Hier liegen Referenzen und Dateien, die von den Agenten nicht verändert werden dürfen, sondern als feste Leitplanken dienen.

*   **`.../knowledge/`**: Deine Wissensdatenbank.
    *   `global/`: Übergreifende Format- und Stilvorlagen (z. B. der allgemeine Brand Voice).
    *   `copywriter/`: Spezifische Textausschlüsse (Blacklists) für den Schreiber.
*   **`.../pipeline/input/`**: Hier legst du deine neuen Kampagnen-Briefings ab. Dies ist der Startpunkt für jeden neuen Durchlauf deines Departments.

---

### Bereich 3: `03_ИЗМЕНЕНИЕ_ДЛЯ_ТРЕТ_РАУНДА` (Änderungs- und Update-Verzeichnis)
*   **`.../readme.md`**: Ein historischer Index, der als Revisionsprotokoll dient, um Änderungen an den Agenten über mehrere Testrunden hinweg sauber zu dokumentieren.

---

## 📄 3. Vollständiges Datei- und Inhaltsverzeichnis

Jede Datei, die durch dein Installationsskript angelegt wird, ist bereits mit praxiserprobten Inhalten und Regeln vorstrukturiert.

| Exakter Dateipfad | Zweck & Funktion | Vorstrukturierter Inhalt |
| :--- | :--- | :--- |
| `01_ПРОЕКТ-ОТДЕЛА/.claude/settings.json` | Steuert globale Department-Features wie Veto-Schleifen. | Definiert das Modell `claude-3-5-sonnet`, aktiviert das automatische Veto-Handling und setzt die Pfade für Critic-Regeln und Output fest. |
| `01_ПРОЕКТ-ОТДЕЛА/ЗАДАЧА.md` | Die übergeordnete Zielsetzung des gesamten Departments. | Beschreibt die Probleme klassischer Ein-Prompt-KI (Halluzinationen, Floskeln) und erklärt die Lösung durch Rollenisolierung. |
| `01_ПРОЕКТ-ОТДЕЛА/AGENTS.md` | Kurzübersicht aller Rollen für Entwickler. | Listet die 5 Rollen (Manager, Researcher, Marketer, Copywriter, QA Critic) und ihre grundlegenden Aufgaben auf. |
| `01_ПРОЕКТ-ОТДЕЛА/employees/copywriter/instructions.md` | Der unzensierte System-Prompt des Copywriters. | Schreibt das Zwei-Fassungen-Prinzip (Kurz & Lang) vor und definiert die goldene Brand Voice (Kurze Sätze, direktes "Du"). |
| `01_ПРОЕКТ-ОТДЕЛА/employees/critic/instructions.md` | Die strenge System-Instruktion des Qualitätsprüfers. | Verbietet dem Critic das Selberschreiben. Schreibt die 7-Punkte-Checkliste und das Veto-Protokoll (REJECTED) vor. |
| `01_ПРОЕКТ-ОТДЕЛА/employees/marketer/instructions.md` | Die strategische Arbeitsanweisung des Marketers. | Weist den Marketer an, aus den Fakten 3 Buyer Personas, ein USP und eine Angebots-Treppe zu bauen (ohne Werbetexte zu verfassen). |
| `01_ПРОЕКТ-ОТДЕЛА/employees/researcher/instructions.md` | Das Regelwerk für neutrale Faktenrecherche. | Verbietet jegliche werbliche Sprache. Schreibt die Pflicht zur URL-Verifizierung und das strikte Verbot von Erfindungen vor. |
| `01_ПРОЕКТ-ОТДЕЛА/output/copywriter/texts.md` | Protokolliert die Entstehung der Texte. | Enthält ein echtes Beispiel einer gescheiterten Erstfassung (Draft 1 - REJECTED) aufgrund von Blacklist-Floskeln und wie der Critic reagierte. |
| `01_ПРОЕКТ-ОТДЕЛА/output/marketer/strategy.md` | Speicherort der Marketingstrategie. | Ein strukturiertes Template für die 3 Zielgruppensegmente und das ausgearbeitete Verkaufsversprechen (USP). |
| `01_ПРОЕКТ-ОТДЕЛА/output/researcher/source-1.md` | Datenquelle 1 (Faktenrecherche). | Beispielhafte, verifizierte Marktfakten (z. B. "35 % aller Kundenanfragen im Autosektor kommen nachts"). |
| `01_ПРОЕКТ-ОТДЕЛА/output/researcher/source-2.md` | Datenquelle 2 (Faktenrecherche). | Analysen zur Arbeitszeitersparnis und Prozessbeschleunigung durch den Einsatz von KI. |
| `01_ПРОЕКТ-ОТДЕЛА/output/researcher/source-3.md` | Datenquelle 3 (Faktenrecherche). | Genaue Spezifikationen und Zeitrahmen für CRM-Schnittstellen und Software-Anbindungen. |
| `01_ПРОЕКТ-ОТДЕЛА/final/test-run.md` | Das erfolgreiche Archiv. | Das finale Freigabeprotokoll mit dem Stempel `✅ APPROVED` durch den QA Critic. |
| `02_ПРОЕКТ-ПАПКИ-НЕ-АГЕНТЫ/readme.md` | Archiv-Wegweiser. | Erklärt, dass dieser Ordner für unveränderliche, globale Brand-Richtlinien reserviert ist. |
| `02_ПРОЕКТ-ПАПКИ-НЕ-АГЕНТЫ/knowledge/global/brand_voice_template.md` | Übergreifende Corporate Identity Richtlinie. | Definiert den Tone of Voice für das gesamte Unternehmen: Pragmatismus, Nutzenorientierung, Fokus auf harte Beweise. |
| `02_ПРОЕКТ-ПАПКИ-НЕ-АГЕНТЫ/knowledge/copywriter/forbidden_phrases_template.md` | Die Zensur- und Verbotsliste. | Liste mit exakten Begriffen, die verboten sind (z. B. "revolutionär", "ultimativ", "Spitzenklasse"). |
| `02_ПРОЕКТ-ПАПКИ-НЕ-АГЕНТЫ/pipeline/input/briefing_template.md` | Muster-Briefing für neue Kampagnen. | Ein leeres, strukturiertes Formular für Ziele, Budget, Produktmerkmale und Zielvorgaben des Kunden. |
| `03_ИЗМЕНЕНИЕ_ДЛЯ_ТРЕТ_РАУНДА/readme.md` | Revisions- und Updateprotokoll. | Übersicht über historisch vorgenommene Prompt-Optimierungen und Department-Anpassungen. |

---

## 🔒 4. Die Sicherheits- und Rechte-Matrix (Wer darf was?)

Um Fehler, Überschreiben oder unbefugtes Manipulieren von Systemdateien durch Agenten zu verhindern, gilt in der `subagents_department`-Struktur eine strikte Rechteverteilung:

| Rolle (Agent) | Leserechte (READ) | Schreibrechte (WRITE) | Berechtigungsgrenzen |
| :--- | :--- | :--- | :--- |
| **Manager** | Gesamtes Projekt, `pipeline/input/`, `output/` | `.claude/settings.json`, Aufgabenverteilungen | Darf niemals selbst Entwürfe schreiben oder den Critic-Zensurordner ändern. |
| **Researcher** | `pipeline/input/`, `knowledge/` | `output/researcher/` | Darf keine Marketingtexte oder Zielgruppensegmente entwerfen. |
| **Marketer** | `output/researcher/`, `knowledge/` | `output/marketer/` | Darf keine fertigen Werbe-Anzeigen formulieren. |
| **Copywriter** | `output/marketer/`, `knowledge/` | `output/copywriter/` | Darf keine Fakten erfinden; ist an die Blacklist in `knowledge/` gebunden. |
| **QA Critic** | `output/copywriter/`, `knowledge/` | `final/`, `output/copywriter/texts.md` (nur Feedback-Log) | **Hat absolutes Schreibverbot für Texte!** Darf nur absegnen (`APPROVED`) oder blockieren (`REJECTED`). |
