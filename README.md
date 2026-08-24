Dieses Repository enthält die technische Spezifikation, die Infrastrukturvorgaben und die operativen Protokolle für  Codex-Alpha , eine hocheffiziente Multi-Agenten-Architektur. Als Senior AI Solutions Architect ist dieses Dokument als verbindliches System-Manifest für die industrielle Skalierung von KI-Workflows zu betrachten.
1. Das Projekt-Manifest (README.md)
Strategische Analyse: Der Paradigmenwechsel
Die herkömmliche Nutzung von KI über isolierte Prompts stößt in komplexen industriellen Umgebungen an kognitive Grenzen. „Codex-Alpha“ markiert einen Paradigmenwechsel hin zur agentenbasierten Kapselung (Encapsulation). Durch die Trennung von Rollen in einem geschlossenen System werden menschliche Engpässe eliminiert und die kognitive Last verteilt. Diese Architektur ist für die industrielle Skalierbarkeit unerlässlich, da sie den Nutzer vom direkten Zugriff auf Sub-Agenten isoliert. Dies schützt das System vor inkonsistenten Anweisungen („Prompt-Injection“) und stellt sicher, dass spezialisierte Micro-Identitäten ihre Integrität wahren.
1.1 System-Architektur & Multi-Agenten-Graph
Das Department operiert nach dem  „Single Point of Contact“-Prinzip . Der Nutzer interagiert ausschließlich mit der Führungsebene, die als Orchestrator fungiert.Die fünf Agenten-Rollen:
Managing Director / Руководитель (Управляющий агент)
Mission:  Zentraler Orchestrator und COO. Er analysiert das Briefing aus 01_ПРОЕКТ-ОТДЕЛА, delegiert Aufgaben und führt die Ergebnisse erst nach expliziter QA-Freigabe zusammen.
Constraints:  Keine direkte Kommunikation von Rohdaten an den Nutzer; lückenlose Protokollierung jedes Schritts in der process.md.
Researcher / Исследователь
Mission:  Datendetektiv für Marktintelligenz. Zur Vermeidung von Bias und zur Erhöhung der Validität arbeiten  drei parallele Instanzen  (Multi-Perspective Validation), die getrennt die Bereiche  Konkurrenz, Zielgruppe und Markttrends  beleuchten.
Constraints:  Absolute Neutralität.  Formatierungspflicht: Markdown-Tabellen für Datenvergleiche.  Jede Behauptung muss durch eine URL und einen Zeitstempel in der 06_QUELLEN.md belegt sein.
Marketer / Маркетолог
Mission:  Strategisches Gehirn. Transformiert Researcher-Daten in ein Positionierungspapier. Er definiert exakt drei Buyer Personas, den USP und die psychologische Trigger-Matrix.
Constraints:  Striktes Verbot der Werbetext-Erstellung; Fokus liegt rein auf dem „Strategie-Skelett“.
Copywriter / Копирайтер
Mission:  Psychologische Conversion-Optimierung. Erstellt basierend auf der Strategie Werbetexte unter Anwendung der PAS- und AIDA-Frameworks.
Constraints:  Erstellung einer Kurz- und Langfassung für jedes Asset; absolute Einhaltung der Zensurliste (Forbidden Phrases).
QA Critic / Критик (Контроль качества)
Mission:  Unbestechlicher Gatekeeper. Prüft alle Agenten-Outputs gegen die 7-Punkte-Checkliste.
Constraints:  Darf keine Texte selbst umschreiben; agiert rein über binäre Entscheidungen:  „FREIGEBEN“ (APPROVED)  oder  „NICHT FREIGEBEN / НЕ ВЫПУСКАТЬ“ (REJECTED) .
1.2 Die physische Infrastruktur (Datei- & Ordnerstruktur)
Die Systemintegrität wird durch ein dateibasiertes  State Management  sichergestellt. Die Ordnerstruktur fungiert als das „Langzeitgedächtnis“ des Departments. Das System-Manifest befindet sich in der .codex/settings.json, welche die technischen Spielregeln erzwingt.
.
├── .codex/                    # Verstecktes System-Verzeichnis (Manifest & Logik)
│   └── settings.json          # Zentrale Konfiguration (System-ID, Pfade, QA-Loop)
├── 00_СТАРТ-В-CHATGPT-DESKTOP.md # Zentraler Einstiegspunkt
├── 01_ПРОЕКТ-ОТДЕЛА           # Operatives Agenten-Archiv
│   ├── ЗАДАЧА.md              # Übergeordnetes Zieldokument (Mission)
│   ├── AGENTS.md              # Definition der Rollen & Constraints
│   ├── employees/             # System-Prompts (instructions.md) pro Rolle
│   ├── output/                # Dynamische Zwischenergebnisse (Rohdaten)
│   └── final/                 # Verifiziertes Endarchiv (Absolutes Tabu für Entwürfe)
├── 02_ПРОЕКТ-ПАПКИ-НЕ-АГЕНТЫ  # Statische Wissensdatenbank (Assets)
│   ├── knowledge/             # Schreibrichtlinien & Zensurliste
│   └── pipeline/              # Arbeitsordner (input/ für Briefings, interim/ für Verarbeitung)
├── 02_ПРОМПТЫ.md              # Datenbank der Master-Instruktionen
├── 03_ИЗМЕНЕНИЕ_ДЛЯ_ТРЕТЬЕГО_РАУНДА # Optimierungs-Protokoll (Versionskontrolle)
├── 03_ЭКСПЕРИМЕНТЫ.md         # Sandkasten für A/B-Tests
├── 04_ЧЕКЛИСТ-СЪЁМКИ.md       # Produktionsvorgaben visuell
├── 05_КАРТОЧКА-СРАВНЕНИЯ.md   # Wettbewerbs-Matrix
├── 06_ИСТОЧНИКИ.md            # Verzeichnis verifizierter Datenquellen (URLs)
└── 07_ОТЧЁТ-ПРОВЕРКИ.md       # Audit-Log der Qualitätskontrolle (Critic)


Hinweis: Der  final/  -Ordner dient als Endpunkt des State Managements. Daten werden erst nach dem Critic-Votum vom Manager hierher verschoben.
1.3 Die unbestechliche Qualitätskontrolle (Veto-Schleife)
Der QA Critic ist der strategische Sicherheitsanker. Die  7-Punkte-Checkliste  ist bindend:
Quellen-Validität:  Sind alle Fakten mit funktionierenden URLs/Zeitstempeln aus 06_QUELLEN.md belegt?
Tonalitäts-Check:  Entspricht der Entwurf zu 100% dem Brand-Code?
Zensurfilter:  Wurden verbotene Phrasen (siehe unten) verwendet?
Logik-Audit:  Unterstützen die Research-Daten konsistent die Marketing-Strategie?
Struktur-Check:  Liegen sowohl PAS- als auch AIDA-Versionen vor?
Vollständigkeit:  Sind Kurz- und Langfassungen für alle Kanäle vorhanden?
Halluzinations-Prüfung:  Gibt es statistische Ausreißer ohne Primärnachweis?Der Blocker-Prozess:  Bei Fehlern setzt der Critic den Status auf  „NICHT FREIGEBEN / НЕ ВЫПУСКАТЬ“ . Dies löst eine automatische Rückdelegation via Manager an den verursachenden Agenten aus. Es gilt eine Zero-Tolerance-Rule für Halluzinationen.Zensurliste (Forbidden Phrases):
„In der heutigen digitalen Welt...“
„Bahnbrechend“ / „Revolutionär“
„Maximieren Sie Ihren Erfolg“
„Lösung aus einer Hand“
„Synergieeffekte nutzen“
„KI-gestützte Magie“
1.4 Installations- und Betriebsanweisungen
Zur Inbetriebnahme muss die .codex/settings.json an die lokale Umgebung angepasst werden. Nach der Konfiguration wird das System durch den Master-Prompt initialisiert.Verbindungssatz:  Nachdem die strukturellen Rahmenbedingungen definiert sind, folgt die technische Absicherung der Arbeitsumgebung durch die Konfigurationsdateien.
2. Sicherheits- und Ausschlussregeln (.gitignore)
In einer professionellen Architektur ist Datensouveränität nicht optional. Die .gitignore schützt sensible System-Instruktionen und verhindert die Korruption des Audit-Trails durch temporäre Session-Daten.
2.1 Die vorkonfigurierte .gitignore-Vorlage
# macOS Spezifisch
.DS_Store
.AppleDouble
.LSOverride


# Python / Umgebung
__pycache__/
*.py[cod]
*$py.class
.venv/
env/
venv/
.env


# Codex System & Security
# Lokale Session-Logs ausschließen, System-Manifest bewahren
.codex/logs/
*.log


# Projekt-Artefakte & State Management
# Temporäre Verarbeitungsdaten in der Pipeline ausschließen
02_ПРОЕКТ-ПАПКИ-НЕ-АГЕНТЫ/pipeline/interim/*
01_ПРОЕКТ-ОТДЕЛА/output/*/interim_*
01_ПРОЕКТ-ОТДЕЛА/output/researcher/source-*.md


# AUSNAHMEN: Diese Dateien sind kritisch für das System-Tracking
!.codex/settings.json
!01_ПРОЕКТ-ОТДЕЛА/final/
!07_ОТЧЁТ-ПРОВЕРКИ.md


Verbindungssatz:  Die Sicherung der Umgebung bildet die Basis für den operativen Start des Systems über die Terminal-Steuerung.
3. Operations-Handbuch: Schnellstart-Anleitung
Der Installer recreate_project.py dient der Sicherstellung der  Idempotenz : Er garantiert, dass die Umgebung bei jedem Lauf exakt den Spezifikationen entspricht und keine strukturellen Abweichungen entstehen.
3.1 Initialisierung via Terminal
Voraussetzungen:  Python 3.x Umgebung und Zugriff auf die Claude Code CLI.
Deployment:  Führen Sie den Installer aus: python recreate_project.py.
Validierung:  Überprüfen Sie die Existenz der Kernverzeichnisse (01_... bis .codex/) sowie die Vollständigkeit der instructions.md in den employees/-Ordnern.
3.2 Steuerung des Departments
Die Aktivierung erfolgt über den zweisprachigen Master-Prompt an den  Managing Director / Руководитель :
DE: „Prüfe die Einsatzbereitschaft des Departments. Delegiere die Prüfung der Arbeitsumgebungen parallel an den Researcher und den Critic. Initialisiere danach die Strategieentwicklung für [PROJEKTNAME] gemäß allen Systemregeln.“


RU: „Проверь готовность отдела к запуску. Параллельно делегируй исследователю и критику проверку рабочих мест. После чего запусти цикл разработки стратегии для [PROJEKTNAME] по всем правилам проекта.“


Überwachen Sie den operativen Fortschritt in der process.md und analysieren Sie den Audit-Trail in der 07_ОТЧЁТ-ПРОВЕРКИ.md.
3.3 Wartungs-Routine für Administratoren
  Täglich:  Manuelle Bereinigung temporärer .md-Dateien aus den Agenten-Outputs.  Warum?  Verhindert „Context-Window Pollution“, damit Agenten nicht durch veraltete Zwischenschritte verwirrt werden.
  Wöchentlich:  Audit der 07_ОТЧЁТ-ПРОВЕРКИ.md.  Warum?  Identifikation wiederkehrender Blocker zur gezielten Optimierung der System-Prompts.
  Wöchentlich:  Abgleich der 06_QUELLEN.md und Aktualisierung der Zensurliste in der knowledge/-Datenbank.
  Monatlich:  Pfad-Validierung in der .codex/settings.json und vollständiges System-Backup.

