# API Testing Projekt mit Postman

## Projektübersicht
Dieses Projekt demonstriert die manuelle und automatisierte Testautomatisierung von RESTful APIs unter Verwendung von Postman. Es zielt darauf ab, die Funktionalität verschiedener HTTP-Methoden (GET, POST) auf ausgewählten Ressourcen von zwei unterschiedlichen APIs zu validieren: dem [Tricentis Demo Web Shop](https://demowebshop.tricentis.com/) und der [JSONPlaceholder API](https://jsonplaceholder.typicode.com/).

## Verwendete Technologien
* **Postman:** Eine populäre Plattform für die Entwicklung, das Testen und die Dokumentation von APIs. Sie bietet eine grafische Benutzeroberfläche zur einfachen Interaktion mit APIs.
* **JSON (JavaScript Object Notation):** Ein leichtgewichtiges Daten-Austauschformat, das von den APIs in diesem Projekt verwendet wird.

## Projektstruktur
Das Herzstück dieses Projekts sind die Postman Collections, die eine Sammlung von API-Anfragen enthalten. Die Struktur der Collections und die darin enthaltenen Anfragen sind logisch organisiert, um die Testfälle übersichtlich darzustellen.

![Postman Collection Overview](link_zum_screenshot_deiner_postman_collection.png)
## API-Endpunkte
Dieses Projekt interagiert mit den folgenden API-Endpunkten:

### **1. Tricentis Demo Web Shop API (`https://demowebshop.tricentis.com/`)**
* Get Demo Webshop Homepage (GET)
* Get Product Category - Books (GET)

### **2. JSONPlaceholder API (`https://jsonplaceholder.typicode.com/`)**
* Get All Comments (GET)
* Get All Users (GET)
* Post New Comment (POST)
* Get Non-existent Comment (Negative GET)

## Testfälle (in Postman Collections)
Die API-Anfragen sind in zwei separaten Collections organisiert, um die Testfälle nach der Ziel-API zu gruppieren:

### **Collection: Demo Webshop Tests**
Diese Collection enthält API-Aufrufe, die auf Funktionalitäten des Tricentis Demo Web Shops abzielen. Es handelt sich um simulierte API-Endpunkte, da der eigentliche Webshop primär für UI-Tests konzipiert ist.

* **GET Demo Webshop Homepage:** Sendet eine GET-Anfrage an den simulierten Homepage-Endpunkt.
* **GET Product Category - Books:** Sendet eine GET-Anfrage an den simulierten Produktkategorie-Endpunkt für 'Books'.

### **Collection: JSONPlaceholder API Tests**
Diese Collection fokussiert sich auf die Funktionalitäten der JSONPlaceholder API, einer beliebten Fake-REST-API für Test- und Prototyping-Zwecke.

* **GET All Comments:** Ruft alle Kommentare von der `/comments` API ab.
* **GET All Users:** Ruft alle Benutzer von der `/users` API ab.
* **POST New Comment:** Sendet eine POST-Anfrage an `/comments`, um einen neuen Kommentar zu erstellen.
* **GET Non-existent Comment (Negative Test):** Sendet eine GET-Anfrage an einen Endpunkt, der voraussichtlich keine Ressource zurückgibt (z.B. `/comments/999999999`), um das erwartete Fehlerverhalten (z.B. Statuscode 404 Not Found) zu validieren.

Jede Anfrage in Postman kann manuell ausgeführt werden, um die Response (Statuscode, Body, Header, Ladezeit) zu überprüfen. Tests (Assertions) sind direkt in den "Tests"-Tabs der Anfragen integriert, um automatische Validierungen der API-Antworten durchzuführen.

## Ausführung der Tests

### Manuelle Ausführung in Postman
1.  **Postman öffnen:** Starten Sie die Postman-Desktop-Anwendung.
2.  **Collection(s) importieren:**
    * Klicken Sie auf **"Import"** im Postman-Dashboard.
    * Wählen Sie die `.json`-Dateien Ihrer Collections (z.B. `Demo Webshop Tests.postman_collection.json` und `JSONPlaceholder API Tests.postman_collection.json`) aus diesem Projektverzeichnis und importieren Sie diese.
3.  **Anfragen ausführen:**
    * Wählen Sie in der linken Seitenleiste die gewünschte Collection und dann die Anfrage aus.
    * Klicken Sie auf den **"Send"**-Button, um die Anfrage auszuführen.
    * Die Antwort wird im unteren Bereich des Bildschirms angezeigt.
    * Überprüfen Sie den **"Test Results"**-Tab (falls vorhanden), um die automatisierten Assertions zu sehen.

### Automatisierte Ausführung (mittels Newman - Optional/Fortgeschritten)
Für die automatisierte Ausführung von Postman Collections in einer CI/CD-Umgebung (wie GitLab CI/CD oder GitHub Actions) kann der **Newman CLI Runner** verwendet werden. Newman ist ein Befehlszeilen-Collection-Runner für Postman.

*(Hinweis: Die Integration von Newman in eine CI/CD-Pipeline erfordert separate Schritte zur Installation von Node.js/npm und Newman sowie eine Anpassung der CI/CD-Konfigurationsdatei (`.gitlab-ci.yml`), um Newman-Befehle auszuführen.)*

### Git-Integration (für Versionskontrolle)
Dieses Projekt ist mit Git für die Versionskontrolle konfiguriert und mit den Remote-Repositorys auf GitHub und GitLab verbunden.
* **GitHub:** `https://github.com/dein-github-username/API-Postman-Project.git`
* **GitLab:** `https://gitlab.com/dein-gitlab-username/API-Postman-Project.git`
    Änderungen an den exportierten `.json`-Dateien können lokal committet und zu diesen Plattformen gepusht werden.

## Ergebnisse und Schlussfolgerung
Dieses Postman-Projekt dient als praktisches Beispiel für das Testen von APIs. Es zeigt die Einfachheit der Interaktion mit RESTful Services und der Validierung von deren Antworten. Die implementierten Testfälle bestätigen die Funktionalität der getesteten API-Endpunkte beider APIs. Postman ist ein vielseitiges Tool für schnelle API-Exploration und manuelle Tests und kann durch Tools wie Newman auch in eine umfassende Automatisierungsstrategie integriert werden.

---
