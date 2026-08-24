🤖 Autonomes Claude KI-Department 
Dieses Repository enthält die vollständige, für Claude Code und Claude 3.5 Sonnet optimierte Infrastruktur für ein autonomes Multi-Agenten-KI-Department. Das System löst das Problem linearer, fehleranfälliger Chat-Prompts durch eine strikte, dateibasierte Rollenisolierung und eine unbestechliche, automatisierte Qualitätsschleife.

📈 Projekt-Status
Status: 🟢 Aktiv / Production-Ready (Migrated to Claude 3.5 Sonnet)
Aktuelle Version: v1.1.0 (Vollständige Migration von ChatGPT Codex-Alpha auf Claude Code vollzogen)
Kompatibilität: Optimiert für macOS-Terminal, Python 3.12+ und das lokale CLI-Tool claude.
🧠 System-Architektur & Rollenisolierung
Anstatt eine einzelne KI mit der gesamten Kampagnenerstellung zu überladen, teilt dieses Framework komplexe Projekte auf fünf hochspezialisierte, isolierte Sub-Agenten auf. Dies verhindert Fehler, eliminiert KI-Schreibschablonen („Wasser“) und sichert eine kompromisslose Faktenbindung.

Die 5 spezialisierten Agenten:
Руководитель отдела (Managing Director / Manager)
Rolle: Der zentrale Orchestrator und einzige Schnittstelle zum Nutzer (Single Point of Contact).
Aufgabe: Liest das Briefing ein, stößt die Pipeline an, delegiert die Aufgaben an die Sub-Agenten und wertet das Feedback des Kritikers aus. Bei einem Veto leitet er die Korrekturanweisungen gezielt zurück an den Copywriter.
Исследователь (Researcher)
Rolle: Der unbestechliche Faktenbeschaffer.
Aufgabe: Sammelt verifizierte Daten, Preise, technische Parameter und Statistiken. Er arbeitet streng nach Whitelist-Quellen, schreibt in einem völlig neutralen Ton und muss jede Aussage mit einer Quelle belegen. Geringste Zweifel oder fehlende Daten deklariert er offen („Keine Daten vorhanden“).
Маркетолог (Marketing Specialist)
Rolle: Der strategic Positionierer.
Aufgabe: Analysiert die Faktenberichte des Researchers. Er erstellt eine präzise Zielgruppen-Segmentierung (3 Buyer Personas mit konkreten Schmerzpunkten), formuliert das unschlagbare Alleinstellungsmerkmal (USP) und baut die Angebotsarchitektur (Lead-Magnet, Tripwire, Core-Offer) auf.
Копирайтер (Copywriter)
Rolle: Der emotionale und verkaufspsychologische Texter.
Aufgabe: Transformiert die Marketingstrategie in packende Werbetexte. Er arbeitet streng nach Brand-Voice-Vorgaben und liefert immer genau zwei Versionen (Version A für Social Media/Telegram, Version B für E-Mail/Landingpages). Er unterliegt einer strikten Zensurliste für verbotene KI-Worthülsen.
Критик качества (QA Critic)
Rolle: Der unbarmherzige Wächter der Markenrichtlinien (Gatekeeper).
Aufgabe: Prüft die fertigen Texte des Copywriters anhand einer harten 7-Punkte-Checkliste auf Faktentreue, Einhaltung der Zensurliste und strukturelle Anforderungen. Er besitzt keine Schreibrechte für die eigentlichen Texte, sondern vergibt ausschließlich ein klares ✅ APPROVED oder ein hartes ❌ REJECTED (VETO) inklusive detaillierter Fehlerberichte.
📂 Datei- und Ordnerstruktur
Das physische State-Management deines Departments wird über eine strikt getrennte Verzeichnishierarchie auf deinem Mac abgebildet. Dadurch weiß Claude Code zu jeder Zeit, in welchem Schritt sich die Pipeline befindet.

Building Autonomous AI Department/
├── 01_ПРОЕКТ-ОТДЕЛА/
│   ├── .claude/
│   │   └── settings.json           # Lokale Projekt- und Verhaltenskonfiguration
│   ├── employees/                  # System-Instruktionen der Agenten
│   │   ├── manager/
│   │   ├── researcher/
│   │   ├── marketer/
│   │   ├── copywriter/
│   │   │   └── instructions.md     # Überarbeitete Copywriter-v2-Richtlinien
│   │   └── critic/
│   │       └── instructions.md     # Die unbestechlichen QA-Prüfregeln
│   ├── output/                     # Arbeitsverzeichnis der Zwischenergebnisse
│   │   ├── researcher/             # source-1.md, source-2.md, source-3.md
│   │   ├── marketer/               # strategy.md
│   │   └── copywriter/             # texts.md (Entwürfe und Veto-Verlauf)
│   ├── final/
│   │   └── test-run.md             # Freigegebene, finale Marketing-Materialien
│   └── ЗАДАЧА.md                   # Globale Zieldefinition des Departments
├── 02_ПРОЕКТ-ПАПКИ-НЕ-АГЕНТЫ/
│   ├── knowledge/                  # Statische Wissensdatenbanken (Brand Voice, Blacklists)
│   └── pipeline/
│       └── input/                  # Hier legst du neue Briefings (briefing.md) ab
├── 03_ИЗМЕНЕНИЕ_ДЛЯ_ТРЕТ_РАУНДА/
└── recreate_project.py             # Der automatische Struktur-Installer für deinen Mac
🔄 Die unbestechliche Veto-Qualitätsschleife (Critic Loop)
Das Herzstück des fehlerfreien Betriebs ist die automatisierte Kontrollschleife zwischen Copywriter und QA Critic:

[ Briefing ] ──> [ Manager ] ──> [ Researcher ] ──> [ Marketer ] ──> [ Copywriter ]
                                                                             │
                                                                             ▼
[ Finaler Ordner ] <── [ APPROVED ] <── [ QA Critic ] <── [ VETO / REJECTED ] ┘
Der Copywriter schreibt seinen Textentwurf in output/copywriter/texts.md.
Der QA Critic liest den Entwurf und vergleicht ihn mit den Fakten aus output/researcher/ und den Schreibverboten aus der Wissensdatenbank.
Findet der Critic auch nur einen einzigen Fehler (z. B. das verbotene Wort "revolutionär" oder eine erfundene Preisangabe), deklariert er ein VETO:
Er setzt den Status auf ❌ REJECTED (VETO).
Er listet die exakten Fehler unter BLOCKERS auf.
Er formuliert präzise Arbeitsanweisungen unter INSTRUCTION.
Der Manager blockiert die Weitergabe an den Kunden, fängt das Veto ab und übergibt die Korrekturaufgabe zurück an den Copywriter.
Der Copywriter korrigiert den Text punktgenau. Dieser Kreislauf wiederholt sich so lange, bis der Critic ein grünes ✅ APPROVED erteilt. erst dann wandert das Dokument in den Ordner final/.
🛠️ Schnellstart-Anleitung
1. Repository klonen & Ordner öffnen
Navigiere im Terminal deines Mac in das geklonte Projektverzeichnis:

cd ~/Desktop/"Building Autonomous AI Department"
2. Projektstruktur initialisieren
Führe das mitgelieferte Python-Skript aus, um die gesamte Ordnerstruktur inklusive aller System-Instruktionen und Konfigurationsdateien auf deinem Mac aufzubauen:

python3 recreate_project.py
3. Claude Code starten
Starte das interaktive Claude-Terminal-Tool direkt im Hauptverzeichnis:

claude
4. Pipeline-Befehl erteilen
Gib Claude im Terminal den Befehl, die Abteilung für ein neues Briefing arbeiten zu lassen:

Lies das Briefing in 02_ПРОЕКТ-ПАПКИ-НЕ-АГЕНТЫ/pipeline/input/ an, starte die Pipeline über den Manager und führe den gesamten Prozess (Recherche, Strategie, Textentwurf und QA-Kritik) autonom durch. Schreibe die fertigen Texte erst nach Freigabe durch den Critic in den final-Ordner.
📄 Lizenz
Dieses Projekt ist unter der MIT-Lizenz lizenziert. Du darfst den Code frei verwenden, modifizieren, kopieren und sowohl für private als auch kommerzielle Zwecke nutzen.

Die vollständigen Lizenzbedingungen findest du in der separaten Datei LICENSE im Hauptverzeichnis.
